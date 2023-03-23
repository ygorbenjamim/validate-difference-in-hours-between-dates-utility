# validate-difference-in-hours-between-dates-utility

Função utilitária que valida se a data informada é válida em comparação a data atual.

```js
function validateDifferenceInHoursBetweenDates(params) {
  const today = new Date();
  const dateEntered = new Date(params.date);
  var differenceInMilliseconds =
    params.compareWith == "future" ? dateEntered - today : today - dateEntered;
  //const differenceInDays = differenceInMilliseconds / 86400000;
  const differenceInHours = differenceInMilliseconds / 3600000;
  if (differenceInHours >= params.differenceLimit) return true;
  return false;
}

// Uso
/*
const params = {
    date: '2023-03-23 12:22:00',
    differenceLimit: 2,
    compareWith: 'past'
}

const valid = validateDifferenceInHoursBetweenDates(params);
*/
```
