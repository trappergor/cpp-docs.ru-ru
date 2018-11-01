---
title: Записи пользователя
ms.date: 10/22/2018
f1_keywords:
- COLUMN_ENTRY_MAP
helpviewer_keywords:
- rowsets [C++], accessors
- COLUMN_ENTRY macro
- COLUMN_ENTRY_MAP macro
- user records, OLE DB consumer templates
- OLE DB consumer templates, user records
- CAccessor class, example
- BEGIN_ACCESSOR_MAP macro
- accessors [C++], rowsets
- accessors [C++], static
- BEGIN_ACCESSOR macro, example
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
ms.openlocfilehash: 4d52c36368b9b39815cbb9a103f84f140626ba2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567444"
---
# <a name="user-records"></a>Записи пользователя

Чтобы использовать статический метод доступа (то есть, производным от `CAccessor`), потребитель должен иметь запись пользователя. Запись пользователя — это класс C++, который содержит элементы данных для обработки ввода или вывода. **Мастер потребителя ATL OLE DB** создает запись пользователя для поставщика. Можно добавить методы для записи пользователя для дополнительных задач, таких как обработка команд.

Ниже приведен пример записи, обрабатывает команды. В записи пользователя BEGIN_COLUMN_MAP представляет набор строк данных, передаваемых потребителю от поставщика. BEGIN_PARAM_MAP представляет набор параметров команды. В этом примере используется [CCommand](../../data/oledb/ccommand-class.md) класс для обработки параметров команды. Члены данных в записях карты представляют собой смещения в один непрерывный блок памяти для каждого экземпляра класса. Макросы COLUMN_ENTRY соответствуют PROVIDER_COLUMN_ENTRY в на стороне поставщика.

Дополнительные сведения о макросах COLUMN_MAP и PARAM_MAP см. в разделе [макросы для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()

// Parameter binding map
BEGIN_PARAM_MAP(CArtists)
   COLUMN_ENTRY(1, m_nAge)
END_PARAM_MAP()
};
```

## <a name="wizard-generated-user-records"></a>Записи пользователя, созданные мастером

Если вы используете **Мастер потребителя ATL OLE DB** для создания объекта-получателя, вы можете выбрать использование шаблонов OLE DB или атрибутов OLE DB. Созданный код отличается в каждом конкретном случае. Дополнительные сведения об этом коде см. в разделе [классы внедренных](../../data/oledb/consumer-wizard-generated-classes.md).

## <a name="user-record-support-for-multiple-accessors"></a>Поддержка записей пользователя для нескольких методов доступа

Подробное описание сценариев, в которых необходимо использовать несколько методов доступа, см. в разделе [с помощью нескольких методов доступа в наборе строк](../../data/oledb/using-multiple-accessors-on-a-rowset.md).

В следующем примере показано запись пользователя, измененная для поддержки нескольких методов доступа в наборе строк. Вместо того чтобы BEGIN_COLUMN_MAP и END_COLUMN_MAP, он использует [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) и [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) для каждого метода доступа. BEGIN_ACCESSOR-макрос указывает номер объекта доступа (начиная с нуля) и является ли метод доступа объект автоматическим. Вызов автоматические `GetData` для получения данных автоматически во время вызова [MoveNext](../../data/oledb/crowset-movenext.md). Неавтоматические объекты доступа требуют явного извлечения данных. Используйте неавтоматические метод доступа, при привязке к полю данных большого объема (например, растровое изображение), вы не можете получить для каждой записи.

```cpp
class CMultiArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor
    COLUMN_ENTRY(1, m_szFirstName)
    COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor
    COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)