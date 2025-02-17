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

## Crear un webhook
en la terminal ejecutar:
```
stripe listen --forward-to http://localhost:3003/payments/webhook
```
teniendo en cuenta que la url es la que preparamos para nuestro webhook.
importante : no cerrar la terminal en la que ejecutamos esto.

## Activar eventos en stripe
abrimos una nueva terminal y ejecutamos:
```
stripe trigger payment_intent.succeeded
```
esto simulara un pago exitoso.

## Empezamos a gerstionar los eventos del hebhook
vemos primero el signature que nos envia lanzando el trigger.
y seguimos configurando lo necesario en las llamadas 


## Crear un endpoint para recibir el webhook
- para esto vamos a usar Hookdeck
- vamos a la web
```
https://hookdeck.com/
```
- entramos a nuestra cuenta
- tenemos un tier gratuito que nos permite 1000 eventos al mes.

- terminamos la configuracion de el endpoint ern hookdeck
- copiamos la url que nos da hookdeck
- seguimos los igyuientes pasos en 