# Northwind@MongoDB
Fork do repositório [leisenstein/northwind-mongo](https://github.com/leisenstein/northwind-mongo), que por sua vez foi forked de [tmcnab/northwind-mongo]. Créditos a (@shayden)[https://github.com/shayden] pelo dump em CSV.

## O que é
- Um dump simples de dados do banco Northwind (SQL) para CSV
- Arquivo CSV original (northwind.csv) dividido em múltiplos CSVs
- Script de importação para MongoDB (mongo-import.sh)

## Limitações
- Não inclui imagens de funcionários/produtos
- É um dump direto - sem relações ou transformações especiais
- Créditos a @shayden pelo dump CSV. "Buyer beware" (uso por sua conta e risco)

## Coleções a serem criadas

### Employees
- Contém array de `Territories []`

### Customers
- Contém array de `Order []`

### Orders
- Contém array de `Order-Details []`
- Chaves estrangeiras:
  - `CustomerID`
  - `EmployeeID`
  - `ShipperID` (mapeado de "ShipVia")

### Order-Details
- Chaves estrangeiras:
  - `OrderID`
  - `ProductID`

### Products
- Chaves estrangeiras:
  - `SupplierID`
  - `CategoryID`

### Territories
- Chave estrangeira:
  - `RegionID`
