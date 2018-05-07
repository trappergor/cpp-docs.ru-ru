---
title: AtlTraceErrorRecords | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.AtlTraceErrorRecords
- ATL::AtlTraceErrorRecords
- AtlTraceErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- AtlTraceErrorRecords function
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afea3c3ef1f169e5f1cb5fc675c74b54da1be0d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="atltraceerrorrecords"></a>AtlTraceErrorRecords
Выводит записи об ошибке OLE DB сведения об устройстве дампа, если возвращается сообщение об ошибке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      inline void AtlTraceErrorRecords(HRESULT hrErr = S_OK);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hErr`  
 [in] `HRESULT` Возвращенных функции-члена шаблона потребителя OLE DB.  
  
## <a name="remarks"></a>Примечания  
 Если `hErr` не `S_OK`, `AtlTraceErrorRecords` выводит записи об ошибке OLE DB сведения об устройстве дампа ( **отладки** вкладки в окне вывода или файл). Данные записи об ошибке, получаемое от поставщика, включает номер строки, источник, описание, файл справки, контекст и идентификатор GUID для каждой операции записи ошибки. `AtlTraceErrorRecords` выводит эти сведения только в отладочных построениях. В сборках выпуска это пустую заглушку, которая оптимизирована out.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [Класс CDBErrorInfo](../../data/oledb/cdberrorinfo-class.md)