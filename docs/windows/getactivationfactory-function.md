---
title: Getactivationfactory-функция | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3fe0d03ead29362ea2926f6326557df2ba6a2cd9
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649251"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory - функция
Извлекает фабрику активации для типа, указанного в параметре шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Параметр шаблона, который определяет тип фабрики активации.  
  
 *activatableClassId*  
 Имя класса, который может создать фабрика активации.  
  
 *фабрики*  
 После завершения операции, ссылка на фабрику активации для типа *T*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Windows::Foundation  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Windows::Foundation](../windows/windows-foundation-namespace.md)