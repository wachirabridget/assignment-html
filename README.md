# Base class for Electronic Device
class ElectronicDevice:
    def __init__(self, brand, model, year):
        self.brand = brand
        self.model = model
        self.year = year
    def display_info(self):
        return f"{self.brand} {self.model}, {self.year}"
# Derived class for Smartphone with additional functionality
class Smartphone(ElectronicDevice):
    def __init__(self, brand, model, year, storage, camera_megapixels):
        super().__init__(brand, model, year)
        self.storage = storage
        self.camera_megapixels = camera_megapixels
    def display_info(self):
        basic_info = super().display_info()
        return f"{basic_info}, Storage: {self.storage}GB, Camera: {self.camera_megapixels}MP"
    def make_call(self, number):
        print(f"Calling {number}...")
    def take_photo(self):
        print(f"Taking a photo with {self.camera_megapixels}MP camera.")

# Create a Smartphone object
smartphone = Smartphone("Apple", "iPhone 14", 2023, 128, 12)
print(smartphone.display_info())
smartphone.make_call("123-456-7890")
smartphone.take_photo()


# Base class for Vehicle
class Vehicle:
    def move(self):
        raise NotImplementedError("Subclass must implement abstract method")

# Derived class for Car
class Car(Vehicle):
    def move(self):
        print("Driving 🚗")

# Derived class for Plane
class Plane(Vehicle):
    def move(self):
        print("Flying ✈️")

# Derived class for Boat
class Boat(Vehicle):
    def move(self):
        print("Sailing ⛵")

# Create objects of each class
car = Car()
plane = Plane()
boat = Boat()

# Demonstrate polymorphism
vehicles = [car, plane, boat]
for vehicle in vehicles:
    vehicle.move()  # Different move method based on the object type
