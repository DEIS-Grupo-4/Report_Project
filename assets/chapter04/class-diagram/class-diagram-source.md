# Class Diagram - código fuente Mermaid (3 partes)

## Parte 1: núcleo (IAM, Profile, Booking, Garage y Shared)

```mermaid
classDiagram
    direction LR

    namespace SharedContext {
        class AuditableAbstractAggregateRoot {
            <<MappedSuperclass>>
            -Long id
            -Date createdAt
            -Date updatedAt
        }
    }

    namespace IamContext {
        class Account {
            <<AggregateRoot>>
            -Long id
            -String userName
            -String password
            -String role
            -ProfileId profileId
        }
        class ProfileId {
            <<ValueObject>>
            -Long profileId
        }
    }

    namespace ProfileContext {
        class Profile {
            <<AggregateRoot>>
            -Long id
            -Long userId
            -String firstName
            -String lastName
            -String email
        }
    }

    namespace BookingContext {
        class Booking {
            <<AggregateRoot>>
            -Long bookingId
            -Long userId
            -Long vehicleId
            -Long startLocationId
            -Long endLocationId
            -LocalDateTime reservedAt
            -LocalDateTime startDate
            -LocalDateTime endDate
            -LocalDateTime actualStartDate
            -LocalDateTime actualEndDate
            -String status
            -BigDecimal totalCost
            -BigDecimal discount
            -BigDecimal finalCost
            -String paymentMethod
            -String paymentStatus
            -Double distance
            -Integer duration
            -Double averageSpeed
            -Rating rating
        }
        class BookingIssue {
            <<Entity>>
            -Long id
            -String issue
        }
        class Rating {
            <<ValueObject>>
            -Integer score
            -String comment
        }
    }

    namespace GarageContext {
        class Vehicle {
            <<AggregateRoot>>
            -Long id
            -String brand
            -String model
            -Integer year
            -Integer battery
            -Integer maxSpeed
            -Integer range
            -double weight
            -String color
            -String licensePlate
            -String location
            -String status
            -String type
            -String companyId
            -double pricePerMinute
            -String image
        }
        class VehicleFeature {
            <<Entity>>
            -Long id
            -String feature
        }
    }

    class Location {
        <<AggregateRoot>>
    }
    note for Location "Definida en la Parte 2"

    AuditableAbstractAggregateRoot <|-- Booking
    Account *-- ProfileId
    Booking *-- Rating
    Booking "1" *-- "0..*" BookingIssue : issueEntities
    Vehicle "1" *-- "0..*" VehicleFeature : featureEntities
    Account ..> Profile : profileId
    Profile ..> Account : userId
    Booking ..> Account : userId
    Booking ..> Vehicle : vehicleId
    Booking ..> Location : start/endLocationId
```

## Parte 2: operación (Trip, TravelHistory y Location)

```mermaid
classDiagram
    direction LR

    namespace TripContext {
        class Trip {
            <<AggregateRoot>>
            -Long id
            -Long bookingId
            -Long userId
            -Long vehicleId
            -Long startLocationId
            -Long endLocationId
            -String route
            -Date startDate
            -Date endDate
            -int duration
            -float distance
            -float averageSpeed
            -float maxSpeed
            -float totalCost
            -float carbonSaved
            -int caloriesBurned
            -String weather
            -int temperature
            -String status
        }
        class TripRouteCoordinate {
            <<Entity>>
            -Long id
            -double lat
            -double lng
        }
        class TripIncidentReport {
            <<Entity>>
            -Long id
            -String incidentReport
        }
        class RouteCoordinates {
            <<ValueObject>>
            -double lat
            -double lng
        }
        class TripPhoto {
            <<Entity>>
            -Long id
            -String photo
        }
    }

    namespace TravelHistoryContext {
        class TravelHistory {
            <<AggregateRoot>>
            -Long id
            -Long userId
            -String location
            -String vehicle
            -String image
            -String tripDuration
            -String travelDistance
            -LocalDateTime createdAt
        }
    }

    namespace LocationContext {
        class Location {
            <<AggregateRoot>>
            -Long id
            -String name
            -String address
            -Coordinates coordinates
            -String type
            -int capacity
            -int availableSpots
            -boolean isActive
            -OperatingHours operatingHours
            -String district
            -String description
            -String image
        }
        class LocationAmenity {
            <<Entity>>
            -Long id
            -String amenity
        }
        class Coordinates {
            <<ValueObject>>
            -double lat
            -double lng
        }
        class OperatingHours {
            <<ValueObject>>
            -String open
            -String close
        }
    }

    class Account {
        <<AggregateRoot>>
    }
    note for Account "Definida en la Parte 1"
    class Vehicle {
        <<AggregateRoot>>
    }
    note for Vehicle "Definida en la Parte 1"
    class Booking {
        <<AggregateRoot>>
    }
    note for Booking "Definida en la Parte 1"

    Location *-- Coordinates
    Location *-- OperatingHours
    Location "1" *-- "0..*" LocationAmenity : amenityEntities
    Trip "1" *-- "0..*" TripRouteCoordinate : routeCoordinateEntities
    Trip "1" *-- "0..*" TripIncidentReport : incidentReportEntities
    Trip "1" *-- "0..*" TripPhoto : photoEntities
    Trip ..> RouteCoordinates : getRouteCoordinates()
    Trip ..> Booking : bookingId
    Trip ..> Account : userId
    Trip ..> Vehicle : vehicleId
    Trip ..> Location : start/endLocationId
    TravelHistory ..> Account : userId
```

## Parte 3: soporte (Notifications, Plan y UnlockRequest)

```mermaid
classDiagram
    direction LR

    namespace NotificationsContext {
        class Notification {
            <<AggregateRoot>>
            -Long id
            -String publicId
            -Long userId
            -String title
            -String message
            -String type
            -String category
            -String priority
            -LocalDateTime createdAt
            -LocalDateTime readAt
            -boolean isRead
            -boolean actionRequired
            -String relatedEntityId
            -String relatedEntityType
            -String icon
            -String color
        }
    }

    namespace PlanContext {
        class Plan {
            <<AggregateRoot>>
            -Long id
            -String name
            -String description
            -float price
            -String currency
            -float pricePerMinute
            -String duration
            -int durationDays
            -int maxTripsPerDay
            -int maxMinutesPerTrip
            -int freeMinutesPerMonth
            -int discountPercentage
            -String color
            -boolean isPopular
            -boolean isActive
        }
        class PlanBenefit {
            <<Entity>>
            -Long id
            -String benefit
        }
    }

    namespace UnlockRequestContext {
        class UnlockRequest {
            <<AggregateRoot>>
            -Long id
            -String publicId
            -String userId
            -Long vehicleId
            -Long bookingId
            -Date requestedAt
            -Date scheduledUnlockTime
            -Date actualUnlockTime
            -String status
            -String method
            -Coordinates location
            -String unlockCode
            -int attempts
            -String errorMessage
        }
    }

    class Coordinates {
        <<ValueObject>>
        -double lat
        -double lng
    }
    note for Coordinates "Definido en la Parte 2"
    class Account {
        <<AggregateRoot>>
    }
    note for Account "Definida en la Parte 1"
    class Vehicle {
        <<AggregateRoot>>
    }
    note for Vehicle "Definida en la Parte 1"
    class Booking {
        <<AggregateRoot>>
    }
    note for Booking "Definida en la Parte 1"

    Plan "1" *-- "0..*" PlanBenefit : benefitEntities
    UnlockRequest *-- Coordinates
    UnlockRequest ..> Account : userId
    UnlockRequest ..> Vehicle : vehicleId
    UnlockRequest ..> Booking : bookingId
    Notification ..> Account : userId
```
