- PASARELA DE PAGO

## INSTALAR STRIPE
```
npm install stripe --save
```

## PREPARAR ENVIRONMENT
Actualizar datos en envs config

## conectar stripe en el servicio
```
private readonly stripe = new Stripe(envs.stripeSecret);
```

## configurar payment session
lo preparamos para recibir datos.

ejemplo de postman:
```
{
    "currency": "eur",
    "items": [
        {
            "name": "Teclado Mecanico",
            "price": 100,
            "quantity": 2
        },
        {
            "name": "Raton Mecanico",
            "price": 30.99,
            "quantity": 2
        }
    ]
}
```