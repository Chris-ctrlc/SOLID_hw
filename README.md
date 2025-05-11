# SOLID_hw
**S – Single Responsibility Principle (Принцип единственной ответственности на примере Java)**



```java
public class RentCarService {
    public Order orderCar(String carNo, Client client) {
        //client order car
        return order;
    }
  }
public class PrinterService {
    public void printOrder(Order order) {
        //print order
    }
}
public class CarInfoService {
    public void getCarInterestInfo(String carType) {
        if (carType.equals("sedan")) {
            //do some job
        }
        if (carType.equals("pickup")) {
            //do some job
        }
        if (carType.equals("van")) {
            //do some job
        }
    }
}
public class NotificationService {
    public void sendMessage(String typeMessage, String message) {
        if (typeMessage.equals("email")) {
            //write email
            //use JavaMailSenderAPI
        }
    }
}
public class CarService {
    public Car findCar(String carNo) {
        //find car by number
        return car;
    }
}
```


**O – Open/Closed Principle (Принцип открытости/закрытости на примере C#)**


```C#
public abstract class Shape {
    public abstract double Area();
}

public class Circle : Shape {
    public double Radius { get; set; }

    public override double Area() {
        return Math.PI * Radius * Radius;
    }
}
```

**L – Liskov Substitution Principle (Принцип подстановки Барбары Лисков на примере Python)**


```Python
from abc import ABC, abstractmethod


class Notification(ABC):
    @abstractmethod
    def notify(self, message):
        pass


class Email(Notification):
    def __init__(self, email):
        self.email = email

    def notify(self, message):
        print(f'Send "{message}" to {self.email}')


class SMS(Notification):
    def __init__(self, phone):
        self.phone = phone

    def notify(self, message):
        print(f'Send "{message}" to {self.phone}')


class Contact:
    def __init__(self, name, email, phone):
        self.name = name
        self.email = email
        self.phone = phone


class NotificationManager:
    def __init__(self, notification):
        self.notification = notification

    def send(self, message):
        self.notification.notify(message)


if __name__ == '__main__':
    contact = Contact('John Doe', 'john@test.com', '(408)-888-9999')

    sms_notification = SMS(contact.phone)
    email_notification = Email(contact.email)

    notification_manager = NotificationManager(sms_notification)
    notification_manager.send('Hello John')

    notification_manager.notification = email_notification
    notification_manager.send('Hi John')
```

**I – Interface Segregation Principle (Принцип разделения интерфейсов на примере Java)**


```java
interface Printer {
    void print();
}

interface Scanner {
    void scan();
}

class SimplePrinter implements Printer {
    public void print() {
        System.out.println("Printing");
    }
}
```

**D – Dependency Inversion Principle (Принцип инверсии зависимостей на примере C#)**


```C#
public interface IKeyboard {
    string GetInput();
}

public class StandardKeyboard : IKeyboard {
    public string GetInput() => "User Input";
}

public class Computer {
    private readonly IKeyboard _keyboard;

    public Computer(IKeyboard keyboard) {
        _keyboard = keyboard;
    }

    public void Type() {
        Console.WriteLine(_keyboard.GetInput());
    }
}
```
