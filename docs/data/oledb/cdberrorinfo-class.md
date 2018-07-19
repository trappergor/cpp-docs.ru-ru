---
title: Класс CDBErrorInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDBErrorInfo
- ATL::CDBErrorInfo
- ATL.CDBErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDBErrorInfo class
ms.assetid: 9a5c18a2-ee3e-40f5-ab4c-581288d7f737
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59222e30fe4a0ee7914c4a4d4e8dfa0d6d3a260b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098619"
---
# <a name="cdberrorinfo-class"></a>Класс CDBErrorInfo
Предоставляет поддержку для обработки ошибок OLE DB с помощью OLE DB [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) интерфейса.  
  
## <a name="syntax"></a>Синтаксис

```cpp
class CDBErrorInfo  
```  
  
## <a name="members"></a>Участники  
  
### <a name="methods"></a>Методы  
  
|||  
|-|-|  
|[GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md)|Возвращает все сведения об ошибке, содержащиеся в записи об ошибке.|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|Вызовы [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) получить основные сведения об указанной ошибке.|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|Вызовы [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) для возврата указателя на интерфейс в объекте пользовательских ошибок.|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|Вызовы [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) для возврата **IErrorInfo** указатель интерфейса на указанную запись.|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|Вызовы [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) для определения параметров ошибки.|  
|[GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md)|Возвращает записи об ошибках для указанного объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот интерфейс возвращает один или несколько записей ошибок для пользователя. Вызовите [CDBErrorInfo::GetErrorRecords](../../data/oledb/cdberrorinfo-geterrorrecords.md) первой, чтобы получить количество записей ошибок. После чего вызывается один доступа к функции, например [CDBErrorInfo::GetAllErrorInfo](../../data/oledb/cdberrorinfo-getallerrorinfo.md), чтобы получить сведения об ошибке для каждой записи.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [DBViewer](../../visual-cpp-samples.md)   
 [Шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны объекта-получателя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)