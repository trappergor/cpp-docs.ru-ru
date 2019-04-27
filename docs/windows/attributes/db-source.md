---
title: db_source (C++ атрибут COM)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.db_source
helpviewer_keywords:
- db_source attribute
ms.assetid: 0ec8bbf7-ade2-4899-bf4c-8608b92779bc
ms.openlocfilehash: 884cab78d64c20bef00958f0cc0319281fd69921
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62148111"
---
# <a name="dbsource"></a>db_source

Создает подключение к источнику данных.

## <a name="syntax"></a>Синтаксис

```cpp
[ db_source(db_source, name, hresult) ]
```

### <a name="parameters"></a>Параметры

*db_source*<br/>
Строка подключения, используемая для подключения к источнику данных. Формат строки подключения, см. в разделе [строки соединения и ссылки на данные](/previous-versions/windows/desktop/ms718376(v=vs.85)) в Майкрософт данных Access Components (MDAC) SDK.

*name*<br/>
(Необязательно) При использовании **db_source** в классе, *имя* — это экземпляр объекта источника данных, имеющий **db_source** атрибут, примененный к нему (см. Пример 1). При использовании **db_source** , встроенный в реализации метода, *имя* — переменная (локальный метода), которая может использоваться для доступа к данным источника (см. Пример 2). Передать его *имя* для *source_name* параметр `db_command` должен быть сопоставлен команды в источнике данных.

*hresult*<br/>
Определяет переменную, которая будет получать HRESULT от этой команды базы данных (необязательно). Если переменная не существует, она будет автоматически внедрена с помощью атрибута.

## <a name="remarks"></a>Примечания

**db_source** создает [CDataSource](../../data/oledb/cdatasource-class.md) и [CSession](../../data/oledb/csession-class.md) объект, который представляет соединение с источником данных потребитель OLE DB.

При использовании **db_source** в классе, `CSession` объект становится членом класса.

При использовании **db_source** в методе, этот код выполняется в области действия метода и `CSession` объект создается как локальная переменная.

**db_source** добавляет свойства источника данных, к классу или внутри метода. Он используется в сочетании с `db_command` (который принимает *db_source* *имя* параметра в виде его *source_name* параметр).

Если поставщик атрибутов потребителя применяет этот атрибут к классу, компилятор переименует класс в \_*YourClassName*Accessor, где *YourClassName* — это имя, которое вы присвоили классу. Также компилятор создаст класс с именем *YourClassName*, производный от \_*YourClassName*Accessor.  В представлении классов отображаются оба класса.

Пример того, этот атрибут, используемый в приложении, см. в примерах [AtlAgent](https://github.com/Microsoft/VCSamples) и [MultiRead](https://github.com/Microsoft/VCSamples).

## <a name="example"></a>Пример

В этом примере вызывает **db_source** для класса, чтобы создать подключение к источнику данных `ds` с помощью базы данных Northwind. `ds` является дескриптором для источника данных, который используется внутренне в `CMyCommand` класса.

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
|**Повторяемый**|Нет|
|**Обязательные атрибуты**|Нет|
|**Недопустимые атрибуты**|Нет|

Дополнительные сведения о контекстах атрибутов см. в разделе [Контексты атрибутов](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>См. также

[Атрибуты объекта-получателя OLE DB](ole-db-consumer-attributes.md)
