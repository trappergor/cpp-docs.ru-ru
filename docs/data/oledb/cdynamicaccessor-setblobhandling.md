---
title: CDynamicAccessor::SetBlobHandling | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::SetBlobHandling
- CDynamicAccessor.SetBlobHandling
- ATL::CDynamicAccessor::SetBlobHandling
- SetBlobHandling
- ATL.CDynamicAccessor.SetBlobHandling
dev_langs:
- C++
helpviewer_keywords:
- SetBlobHandling method
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8ee2c2d57f9f413346bb33a178fc3d8fa90439e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095850"
---
# <a name="cdynamicaccessorsetblobhandling"></a>CDynamicAccessor::SetBlobHandling
Задает больших двоичных ОБЪЕКТОВ, обработки значения для текущей строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      bool SetBlobHandling(DBBLOBHANDLINGENUM eBlobHandling);  
```  
  
#### <a name="parameters"></a>Параметры  
 `eBlobHandling`  
 Указывает способ обработки данных больших двоичных ОБЪЕКТОВ. Возможны следующие значения:  
  
-   **DBBLOBHANDLING_DEFAULT**: обрабатывать данные столбца больше, чем `nBlobSize` (как задано в `SetBlobSizeLimit`), а данные большого двоичного ОБЪЕКТА и получить его через `ISequentialStream` или `IStream` объекта. Этот параметр будет пытаться выполнить привязку каждого столбца, содержащего данные, превышающие `nBlobSize` или перечисляются в виде **DBTYPE_IUNKNOWN** как данные большого двоичного ОБЪЕКТА.  
  
-   **DBBLOBHANDLING_NOSTREAMS**: обрабатывать данные столбца больше, чем `nBlobSize` (как задано в `SetBlobSizeLimit`), а данные большого двоичного ОБЪЕКТА и его можно получить через ссылку в выделенной поставщика, потребителя памяти. Этот параметр полезен для таблиц, имеющих более одного столбца больших двоичных ОБЪЕКТОВ, а поставщик поддерживает только один `ISequentialStream` объекта на каждый метод доступа.  
  
-   **DBBLOBHANDLING_SKIP**: пропустить (привязки) столбцов, выбранных как содержащие большие двоичные объекты (метод доступа не привязать или получить значение столбца, но будет по-прежнему получать столбец состояния и длины).  
  
## <a name="remarks"></a>Примечания  
 Необходимо вызвать `SetBlobHandling` перед вызовом **откройте**.  
  
 Метод конструктора [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) задает большой двоичный объект, значение для обработки **DBBLOBHANDLING_DEFAULT**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)