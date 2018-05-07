---
title: Класс CDynamicParameterAccessor | Документы Microsoft
ms.custom: ''
ms.date: 02/14/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDynamicParameterAccessor
- ATL::CDynamicParameterAccessor
- CDynamicParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicParameterAccessor class
ms.assetid: 5f22626e-e80d-491f-8b3b-cedc50331960
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1b9478a5b2cc2190219ce2b297d1908683577c9e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicparameteraccessor-class"></a>Класс CDynamicParameterAccessor

Аналогично [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) , но получает сведения о параметрах для задания, вызвав [ICommandWithParameters](/sql/relational-databases/native-client-ole-db-interfaces/icommandwithparameters) интерфейса.

## <a name="syntax"></a>Синтаксис

```cpp
class CDynamicParameterAccessor : public CDynamicAccessor
```

## <a name="members"></a>Участники

### <a name="methods"></a>Методы

|||
|-|-|
|[CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-cdynamicparameteraccessor.md)|Конструктор.|
|[GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md)|Получает данные параметров из буфера.|
|[GetParamCount](../../data/oledb/cdynamicparameteraccessor-getparamcount.md)|Получает число параметров в методе доступа.|
|[GetParamIO](../../data/oledb/cdynamicparameteraccessor-getparamio.md)|Определяет, является ли указанный параметр входным или выходным.|
|[GetParamLength](../../data/oledb/cdynamicparameteraccessor-getparamlength.md)|Получает длину указанного параметра, сохраненного в буфере.|
|[GetParamName](../../data/oledb/cdynamicparameteraccessor-getparamname.md)|Получает имя указанного параметра.|
|[GetParamStatus](../../data/oledb/cdynamicparameteraccessor-getparamstatus.md)|Получает состояние указанного параметра, сохраненного в буфере.|
|[GetParamString](../../data/oledb/cdynamicparameteraccessor-getparamstring.md)|Получает строковые данные указанного параметра, сохраненного в буфере.|
|[GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md)|Получает тип данных указанного параметра.|
|[SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md)|Задает буфер, используя данные параметра.|
|[SetParamLength](../../data/oledb/cdynamicparameteraccessor-setparamlength.md)|Задает длину указанного параметра, сохраненного в буфере.|
|[SetParamStatus](../../data/oledb/cdynamicparameteraccessor-setparamstatus.md)|Задает состояние указанного параметра, сохраненного в буфере.|
|[SetParamString](../../data/oledb/cdynamicparameteraccessor-setparamstring.md)|Задает строковые данные указанного параметра, сохраненного в буфере.|

## <a name="remarks"></a>Примечания

Для использования этого класса поставщик должен поддерживать интерфейс `ICommandWithParameters` для потребителя.

Сведения о параметрах хранятся в буфере, создаваемом и управляемом данным классом. Получить данные параметров из буфера можно с помощью методов [GetParam](../../data/oledb/cdynamicparameteraccessor-getparam.md) и [GetParamType](../../data/oledb/cdynamicparameteraccessor-getparamtype.md).

Пример, демонстрирующий использование этого класса для выполнения хранимой процедуры SQL Server и получения значений выходных параметров см. в разделе [DynamicConsumer](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/OLEDB/Consumer/DynamicConsumer) пример кода в [Microsoft VCSamples](https://github.com/Microsoft/VCSamples) репозитория в GitHub.

## <a name="requirements"></a>Требования

**Заголовок:** atldbcli.h

## <a name="see-also"></a>См. также

[Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)  
[Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)  
[Класс CAccessor](../../data/oledb/caccessor-class.md)  
[Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)  
[Класс CManualAccessor](../../data/oledb/cmanualaccessor-class.md)  
