---
title: Метод ChainInterfaces::FillArrayWithIid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c795a3a80c48e7fa976807ab3e261fc927d7e104
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644275"
---
# <a name="chaininterfacesfillarraywithiid-method"></a>Метод ChainInterfaces::FillArrayWithIid
Идентификатор интерфейса определяется хранилищ *I0* параметр шаблона в указанном расположении в указанном массиве идентификаторов интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *Индекс*  
 Указатель на значение индекса в *идентификаторы IID* массива.  
  
 *идентификаторы IID*  
 Массив идентификаторов интерфейсов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)