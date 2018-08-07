---
title: Функция MakeAndInitialize | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAndInitialize
dev_langs:
- C++
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cbdb6a312d6658fc880aa43ffc1205378d3935e7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607654"
---
# <a name="makeandinitialize-function"></a>Функция MakeAndInitialize
Инициализирует указанный класс среды выполнения Windows. Используйте эту функцию, чтобы создать экземпляр компонента, который определен в том же модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <typename T, typename I,   
typename TArg1,   
typename TArg2,   
typename TArg3,   
typename TArg4,   
typename TArg5,   
typename TArg6,   
typename TArg7,   
typename TArg8,   
typename TArg9> HRESULT MakeAndInitialize(_Outptr_result_nullonfailure_ I** ppvObject, TArg1 &&arg1, TArg2 &&arg2, TArg3 &&arg3, TArg4 &&arg4, TArg5 &&arg5, TArg6 &&arg6, TArg7 &&arg7, TArg8 &&arg8, TArg9 &&arg9) throw()  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Определяемый пользователем класс, наследуемый от `WRL::RuntimeClass`.  
  
 *TArg1*  
 Тип аргумента 1, который передается в класс указанной среды выполнения.  
  
 *TArg2*  
 Тип аргумента 2, который передается в класс указанной среды выполнения.  
  
 *TArg3*  
 Тип аргумента 3, который передается в класс указанной среды выполнения.  
  
 *TArg4*  
 Тип аргумента 4, который передается в класс указанной среды выполнения.  
  
 *TArg5*  
 Тип аргумента 5, который передается в класс указанной среды выполнения.  
  
 *TArg6*  
 Тип аргумента 6, передаваемое указанного класса среды выполнения.  
  
 *TArg7*  
 Тип аргумента 7, который передается в класс указанной среды выполнения.  
  
 *TArg8*  
 Тип аргумента 8, который передается в класс указанной среды выполнения.  
  
 *TArg9*  
 Тип аргумента 9, который передается в класс указанной среды выполнения.  
  
 *arg1*  
 Аргумент 1, который передается в класс указанной среды выполнения.  
  
 *Arg2*  
 Аргумент 2, который передается в класс указанной среды выполнения.  
  
 *arg3*  
 Аргумент 3, который передается в класс указанной среды выполнения.  
  
 *arg4*  
 Аргумент 4, который передается в класс указанной среды выполнения.  
  
 *arg5*  
 Аргумент 5, который передается в класс указанной среды выполнения.  
  
 *arg6*  
 Аргумент 6, передаваемый в класс указанной среды выполнения.  
  
 *arg7*  
 Аргумент 7, который передается в класс указанной среды выполнения.  
  
 *arg8*  
 Аргумент 8, который передается в класс указанной среды выполнения.  
  
 *arg9*  
 Аргумент 9, передаваемый в класс указанной среды выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение HRESULT.  
  
## <a name="remarks"></a>Примечания  
 См. в разделе [как: непосредственно создания экземпляра компонентов WRL](../windows/how-to-instantiate-wrl-components-directly.md) в этой статье описаны различия между этой функцией и [Microsoft::wrl:: make](../windows/make-function.md)и примеры.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)