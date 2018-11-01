---
title: Класс CXMLAccessor
ms.date: 11/04/2016
f1_keywords:
- ATL::CXMLAccessor
- CXMLAccessor
- ATL.CXMLAccessor
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
- ATL::CXMLAccessor::GetXMLRowData
- ATL.CXMLAccessor.GetXMLRowData
- CXMLAccessor::GetXMLRowData
- CXMLAccessor.GetXMLRowData
- GetXMLRowData
helpviewer_keywords:
- CXMLAccessor class
- GetXMLColumnData method
- GetXMLRowData method
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
ms.openlocfilehash: ff72d672db963a166284c9ea0f7e3e8c1a89d5e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594718"
---
# <a name="cxmlaccessor-class"></a>Класс CXMLAccessor

Позволяет доступ к источникам данных как строковые данные, когда схема хранилища данных (базовая структура).

## <a name="syntax"></a>Синтаксис

```cpp
class CXMLAccessor : public CDynamicStringAccessorW
```

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[GetXMLColumnData](#getxmlcolumndata)|Извлекает сведения о столбце.|
|[GetXMLRowData](#getxmlrowdata)|Извлекает все содержимое таблицы по строкам.|

## <a name="remarks"></a>Примечания

Тем не менее `CXMLAccessor` отличается от `CDynamicStringAccessorW` тем, что она преобразует все данные из хранилища данных в виде XML-данных (с тегами). Это особенно полезно для выходных данных в XML с поддержкой веб-страниц. Имена тегов XML будет как можно точнее соответствовать имена столбцов в хранилище данных.

Используйте `CDynamicAccessor` методов, чтобы получить сведения о столбцах. Используйте эти сведения для столбца для динамического создания метода доступа во время выполнения.

Сведения о столбце хранится в буфере, создаваемом и управляемом данным классом. Получить сведения о столбце с помощью [GetXMLColumnData](#getxmlcolumndata) или получить данные столбцов, строк с помощью [GetXMLRowData](#getxmlrowdata).

## <a name="example"></a>Пример

[!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/cpp/cxmlaccessor-class_1.cpp)]

## <a name="getxmlcolumndata"></a> CXMLAccessor::GetXMLColumnData

Извлекает тип сведения о столбцах таблицы как строка в формате XML-данные, по столбцу.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetXMLColumnData(CSimpleStringW& strOutput) throw();
```

#### <a name="parameters"></a>Параметры

*strOutput*<br/>
[out] Ссылка на буфер строки, содержащий сведения о типе столбца требуется получить. Строка форматируется с именами тега XML, совпадающие с именами столбцов в хранилище данных.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Ниже показано, как сведения о типе столбца форматируется в формате XML. `type` Указывает тип данных столбца. Обратите внимание, что типы данных основаны на типах данных OLE DB, не те базы данных, к которому выполняется доступ.

`<columninfo>`

`<column type = I2/> ColumnName`

`</columninfo>`

## <a name="getxmlrowdata"></a> CXMLAccessor::GetXMLRowData

Получает все содержимое таблицы в виде данных строка в формате XML, по строкам.

### <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetXMLRowData(CSimpleStringW& strOutput, 
   bool bAppend = false) throw();
```

#### <a name="parameters"></a>Параметры

*strOutput*<br/>
[out] Ссылка на буфер, содержащий данные таблицы требуется получить. Данные форматируются как строковые данные с именами тега XML, совпадающие с именами столбцов в хранилище данных.

*bAppend*<br/>
[in] Логическое значение, указывающее, следует ли добавлять строку в конец выходных данных.

### <a name="return-value"></a>Возвращаемое значение

Одно из стандартных значений HRESULT.

### <a name="remarks"></a>Примечания

Ниже показан способ форматирования строки данных в формате XML. `DATA` ниже представляет строки данных. С помощью предложения move методы для перемещения к требуемой строки.

`<row>`

`<column name>DATA</column name>`

`</row>`

## <a name="see-also"></a>См. также

[Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[Класс CAccessor](../../data/oledb/caccessor-class.md)<br/>
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)<br/>
[Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
[Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)<br/>
[Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)<br/>
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)