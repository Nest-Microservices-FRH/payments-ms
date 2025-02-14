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

## instalar con homebrew el cli de stripe
```
brew install stripe/stripe-cli/stripe
```

web : https://docs.stripe.com/stripe-cli#install

## iniciar stripe
en la terminal ejecutar:
``` 
stripe login
```

## Dar acceso a stripe
en la web seleccionas el proyecto que usas y le das acceso.
este acceso a stripe dura 90 dias.
nos pediran volver a autenticarnos cuando pase ese tiempo.