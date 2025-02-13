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

## 