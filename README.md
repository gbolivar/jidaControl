# JidaControl.js
## Plugin jquery para manejo de controles de Formulario

JidaControl.js es un plugin que permite fijar mascaras de control a los campos de un formulario. Asimismo, tiene varias
**mascaras** por defecto, pero puede ser editado agregando cuantas mascaras se deseen por medio de expresiones regulares.

##Implementacion

### 
***
``` 

	<form role="form">
		  <div class="form-group">
		    <label for="numerico">Numerico</label>
		    <input type="text" class="form-control" id="numerico" placeholder="Ingresa un numero" data-jidacontrol="numerico" maxlength="5">
		  </div>
		  <div class="form-group">
		    <label for="decimales">Decimales</label>
		    <input type="text" class="form-control" maxlength="6" id="decimales" placeholder="Ingresa un numero con decimales" data-jidacontrol="miles" data-decimal="2">
		  </div>
  </form>
 
<script>
	$( document ).ready(function(){
		$("[data-jidacontrol]").jidaControl();
	});
</script>
```
***

## Mascaras disponibles por defecto

	+ **cedula** : Validacion de Cedular o Rif en formato venezolano
	+ **miles** : Validacion númerica son separador de miles, se puede agregar un atributo data-decimal="numeroDecimales"
	+ **caracteres** : Solo caracteres
	+ **Alfanumerico**: Numeros y letras


Las validaciones deben ser agregadas en los controles del formulario por medio del atributo *data-jidacontrol* y pueden ser agregadas cuantas se deseen
por medio del arreglo **json validaciones**.

El Plugin hace uso de tres metodos para el manejo de las mascaras:
+**Controlador** : Ejecuta la expresión solicitada sobre el valor completo del control
+**controladorCaracter**: Ejecuta la expresion solicitada sobre cada tecla presionada, dicho en otras palabras solo evalua la tecla presionada en el momento.
+**controladorDecimal** : Usado para validar campos con separador de miles y decimales
