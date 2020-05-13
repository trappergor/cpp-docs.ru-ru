---
title: db_accessor (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_accessor
helpviewer_keywords:
- db_accessor attribute
ms.assetid: ec407a9f-24d7-4822-96d4-7cc6a0301815
ms.openlocfilehash: 1e9725dad39974b828d87bd8b4cdeac623f4e12f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214868"
---
# <a name="db_accessor"></a>db_accessor

Группирует `db_column` атрибуты, участвующие в привязке на основе `IAccessor`.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_accessor(num, auto) ]
```

#### <a name="parameters"></a>Параметры

*num*<br/>
Указывает номер метода доступа (целочисленный индекс, начинающийся с нуля). Необходимо указать номера методов доступа в порядке возрастания, используя целые числа или определенные значения.

*auto*<br/>
Логическое значение, указывающее, извлекается ли метод доступа автоматически (TRUE) или не извлекается (FALSE).

## <a name="remarks"></a>Remarks

**db_accessor** определяет базовый метод доступа OLE DB для последующих `db_column` и `db_param` атрибутов в пределах одного класса или функции. **db_accessor** можно использовать на уровне членов и используется для группирования `db_column` атрибутов, участвующих в привязке на основе `IAccessor`OLE DB. Он используется в сочетании с атрибутами `db_table` или `db_command`. Вызов этого атрибута аналогичен вызову макросов [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) .

**db_accessor** создает набор строк и привязывает его к соответствующим картам метода доступа. Если не вызвать **db_accessor**, метод доступа 0 будет автоматически создан, и все привязки к столбцам будут сопоставляться с этим блоком доступа.

**db_accessor** группирует привязки столбцов базы данных в один или несколько методов доступа. Обсуждение сценариев, в которых необходимо использовать несколько методов доступа, см. в разделе [Использование нескольких методов доступа в наборе строк](../../data/oledb/using-multiple-accessors-on-a-rowset.md). См. также раздел «Поддержка записи пользователей для нескольких методов доступа» в разделе « [записи пользователей](../../data/oledb/user-records.md)».

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

## <a name="example"></a>Пример

В следующем примере **db_accessor** используется для группировки столбцов в таблице Orders из базы данных Northwind в два способа доступа. Метод доступа 0 является автоматическим методом доступа, а метод доступа 1 — нет.

```cpp
// cpp_attr_ref_db_accessor.cpp
// compile with: /LD /link /OPT:NOREF
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>

[ db_command(L"SELECT LastName, FirstName FROM Orders") ]
class CEmployees {
public:
   [ db_accessor(0, TRUE) ];
   [ db_column("1") ] LONG m_OrderID;
   [ db_column("2") ] TCHAR m_CustomerID[6];
   [ db_column("4") ] DBTIMESTAMP m_OrderDate;

   [ db_accessor(1, FALSE) ];
   [ db_column("8") ] CURRENCY m_Freight;
};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|Блоки атрибутов|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты объекта-получателя OLE DB](ole-db-consumer-attributes.md)
