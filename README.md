### 30/06/2022
## SECTION 6
### 74: Module Introduction
En esta seccion se trata de darle estilo a la aplicacion, darle estilo a los componentes, con diferentes maneras dinamicas y condicionales, por ejemplo tambien manejar el scope de los estilos, aprender de los CSS modules

### Clase 75: Setting dynamic inline styles
En CourseInput.js en el formSubmitHandler queremos verificar si se ingresó algo valido antes de activar la funcion de onAddGoal, asi que agregamos un if() y verificamos el valor entrado, se le da un borde rojo y un dolor de fondo ligeramente rojo al input cuando no ingresa un valor valido.
Se agrego otro state para que sea el indicador de verificar si el usuario igreso algo valido o no, asi que se trata de una opcion verdadera o falsa (boolean): `const [isValid, setIsValid] = useState(true);`
asi que si se considera que esto es verdadero la entrada es valida, pero cuando aplica el if() tenemos que establecerlo como falso, es decir asi: 
```JS
if (enteredValue.trim().lenght === 0) {
      setIsValid(false);
      return;
    }
```
Ahora para ponerle estilos se pone la propiedad en linea de style={{}}(con un objeto dentro), en este caso en el label, pero no se le agrega un estilo normal por que pretendemos que sea dinamico asi que lo queremos configurar solo para cuando la entrada es invalida `<label style={{ color: !isValid ? 'red' : 'black' }}>Course Goal</label>` esto significa que el color si "isValid" es falso sera rojo pero si es correcto sera negro