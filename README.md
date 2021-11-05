# Garpix Order

```python
from garpix_order.models import BaseOrder, BaseOrderItem, BaseInvoice


class Order(BaseOrder):
    pass


class Service(BaseOrderItem):
    def pay(self):
        pass


class Invoice(BaseInvoice):
    pass
```

**BaseOrder** - основной класс заказа.

`items` - метод для получения связанных OrderItem.

`items_amount` - метод для получения суммы оплаты.

**BaseOrderItem** - части заказа. В один заказ можно положить несколько сущностей.

`pay` - метод вызовет у всех BaseOrderItem, когда оплачивается заказ.

`full_amount` - метод возвращает полную сумма заказа. 

**Invoice** - Основная модель для отслеживания статуса оплаты (транзакция). Содержит `status` с типом FSM.

**BasePaymentType** - Абстрактная модель PaymentType для наследования в целях создания модели способа оплаты используемого в проекте.

