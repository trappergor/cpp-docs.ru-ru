---
title: "Метод Implements::CanCastTo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Implements::CanCastTo
dev_langs: C++
helpviewer_keywords: CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 83d217cb749c350da45bcae2159e6b46d03f68cc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="implementscancastto-method"></a>Метод Implements::CanCastTo
Возвращает указатель на указанный интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Ссылку на идентификатор интерфейса.  
  
 `ppv`  
 Если успешно, указатель на интерфейс, заданный `riid`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — значение HRESULT, указывающее ошибку, например E_NOINTERFACE.  
  
## <a name="remarks"></a>Примечания  
 Это внутренняя вспомогательная функция, которая выполняет операцию QueryInterface.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура Implements](../windows/implements-structure.md)