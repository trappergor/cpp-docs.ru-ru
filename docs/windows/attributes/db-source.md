---
title: db_source (C++ атрибут com)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: 6346a8d6f60313dc17bbcbad062aa888857f0b67
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167281"
---
# <a name="db_source"></a>db_source

Создает соединение с источником данных.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>Параметры

*db_source*<br/>
Строка подключения, используемая для подключения к источнику данных. Сведения о формате строки подключения см. в разделе [строки подключения и ссылки на данные](/previous-versions/windows/desktop/ms718376(v=vs.85)) в пакете SDK для компонентов доступа к данным Microsoft (MDAC).

*name*<br/>
Используемых При использовании **db_source** в классе *Name* — это экземпляр объекта источника данных, к которому применен атрибут **db_source** (см. Пример 1). При использовании встроенной **db_source** в реализации метода *Name* — это переменная (локальная для метода), которая может использоваться для доступа к источнику данных (см. Пример 2). Это *имя* передается в параметр *source_name* `db_command`, чтобы связать источник данных с командой.

*hresult*<br/>
Определяет переменную, которая будет получать HRESULT от этой команды базы данных (необязательно). Если переменная не существует, она будет автоматически внедрена с помощью атрибута.

## <a name="remarks"></a>Remarks

**db_source** создает объект [CDataSource](../../data/oledb/cdatasource-class.md) и [CSession](../../data/oledb/csession-class.md) , который вместе представляет соединение с источником данных OLE DB потребителя.

При использовании **db_source** в классе объект `CSession` становятся членом класса.

При использовании **db_source** в методе введенный код будет выполняться в области метода, а объект `CSession` создается как локальная переменная.

**db_source** добавляет свойства источника данных в класс или в метод. Используется в сочетании с `db_command` (принимающий параметр *имени* *db_source* в качестве параметра *source_name* ).

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

Пример использования этого атрибута в приложении см. в разделе [Read](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer).

## <a name="example"></a>Пример

Этот пример вызывает **db_source** для класса, чтобы создать соединение с источником данных `ds` помощью базы данных Northwind. `ds` является обработчиком для источника данных, который можно использовать внутри класса `CMyCommand`.

```cpp
// db_source_1.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlplus.h>
#include <atldbcli.h>

[
  db_source(L"my_connection_string", name="ds"),
  db_command(L"select * from Products")
]
class CMyCommand {};
```

## <a name="requirements"></a>Требования

### <a name="attribute-context"></a>Контекст атрибута

|||
|-|-|
|**Применение**|**class**, **struct**, member, method, local|
|**Повторяемый**|нет|
|**Обязательные атрибуты**|None|
|**Недопустимые атрибуты**|None|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также раздел

[Атрибуты объекта-получателя OLE DB](ole-db-consumer-attributes.md)
