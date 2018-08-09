---
title: Метод Implements::CanCastTo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: a8e85c7d-4dcd-446d-bebc-a97da46ce44a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a73aac6fb36270f0cd04615d9e530b29841850f8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40010926"
---
# <a name="implementscancastto-method"></a>Метод Implements::CanCastTo
Возвращает указатель на указанный интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
__forceinline HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 Ссылку на идентификатор интерфейса.  
  
 *ppv*  
 Если в случае успешного выполнения указатель на интерфейс, заданный *riid*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, указывающее ошибку, например E_NOINTERFACE.  
  
## <a name="remarks"></a>Примечания  
 Это внутренняя вспомогательная функция, которая выполняет операцию QueryInterface.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура Implements](../windows/implements-structure.md)