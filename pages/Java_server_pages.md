É uma tecnologia para desenvolvimento de páginas web dinâmicas utilizando a linguagem java.

## Tópicos

### Estrutura básica

``` html4strict
<%@ page language="java" contentType="text/html; charset=ISO-8859-1" pageEncoding="ISO-8859-1"%>
<!DOCTYPE>
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1">
  <title>Insert title here</title>
</head>
<body>
  Hoje é: <%= new java.util.Date().toLocaleString() %>
</body>
</html>
```
