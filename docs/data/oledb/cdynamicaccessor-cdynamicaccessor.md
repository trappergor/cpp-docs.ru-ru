---
title: CDynamicAccessor::CDynamicAccessor | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDynamicAccessor::CDynamicAccessor
- ATL::CDynamicAccessor::CDynamicAccessor
- ATL.CDynamicAccessor.CDynamicAccessor
- CDynamicAccessor.CDynamicAccessor
dev_langs:
- C++
helpviewer_keywords:
- CDynamicAccessor class, constructor
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 80446719ac8e523efc5ef885fe55fb89561509e4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090605"
---
# <a name="cdynamicaccessorcdynamicaccessor"></a>CDynamicAccessor::CDynamicAccessor
Создает и инициализирует `CDynamicAccessor` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      CDynamicAccessor(DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000);  
```  
  
#### <a name="parameters"></a>Параметры  
 `eBlobHandling`  
 Указывает, каким образом будет обрабатываться данные больших двоичных объектов (BLOB). Значение по умолчанию — **DBBLOBHANDLING_DEFAULT**. В разделе [SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) описание **DBBLOBHANDLINGENUM** значения.  
  
 `nBlobSize`  
 Максимальный размер большого двоичного ОБЪЕКТА в байтах; столбец данных через это значение рассматривается как большой двоичный объект. Значение по умолчанию — 8000. В разделе [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) подробные сведения.  
  
## <a name="remarks"></a>Примечания  
 Если вы используете конструктор для инициализации `CDynamicAccessor` объекта, можно указать, как связать больших двоичных объектов. BLOB-объектов может содержать двоичные данные, например, графики, звук или скомпилированный код. По умолчанию выполняется обрабатывать более 8000 байт столбцы как большие двоичные объекты и попытаться привязать их к `ISequentialStream` объекта. Тем не менее можно указать другое значение для размера большого двоичного ОБЪЕКТА.  
  
 Также можно указать как `CDynamicAccessor` обрабатывает данные столбцов, определяемая как данные большого двоичного ОБЪЕКТА: он может обрабатывать данные большого двоичного ОБЪЕКТА по умолчанию; его можно пропустить (привязки) данных BLOB; или его можно привязать данные большого двоичного ОБЪЕКТА в память, выделенную поставщика.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)