---
title: "Функция Make | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
dev_langs:
- C++
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aac2a50e3c50941d607dea32c9f7c9eecde8e589
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="make-function"></a>Функция Make
Инициализирует указанный класс среды выполнения Windows. Используйте эту функцию, чтобы создать экземпляр компонента, который определен в том же модуле.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8,  
   TArg9 &&arg9  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7,  
   TArg8 &&arg8  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6,  
   TArg7 &&arg7  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5,  
   TArg6 &&arg6  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4,  
   TArg5 &&arg5  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3,  
   TArg4 &&arg4  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2,  
   TArg3 &&arg3  
);  
template <  
   typename T,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<T> Make(  
   TArg1 &&arg1,  
   TArg2 &&arg2  
);  
template <  
   typename T,  
   typename TArg1  
>  
ComPtr<T> Make(  
   TArg1 &&arg1  
);  
template <  
   typename T  
>  
ComPtr<T> Make();  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Определяемый пользователем класс, наследуемый от `WRL::RuntimeClass`.  
  
 `TArg1`  
 Тип аргумента 1, передаваемое указанного класса среды выполнения.  
  
 `TArg2`  
 Тип аргумента 2, передаваемое указанного класса среды выполнения.  
  
 `TArg3`  
 Тип аргумента 3, передаваемое указанного класса среды выполнения.  
  
 `TArg4`  
 Тип аргумента 4, передаваемое указанного класса среды выполнения.  
  
 `TArg5`  
 Тип аргумента 5, передаваемое указанного класса среды выполнения.  
  
 `TArg6`  
 Тип аргумента 6, передаваемое указанного класса среды выполнения.  
  
 `TArg7`  
 Тип аргумента 7, передаваемое указанного класса среды выполнения.  
  
 `TArg8`  
 Тип аргумента 8, передаваемое указанного класса среды выполнения.  
  
 `TArg9`  
 Тип аргумента 9, передаваемое указанного класса среды выполнения.  
  
 `arg1`  
 Аргумент 1, который передается указанного класса среды выполнения.  
  
 `arg2`  
 Аргумент 2, который передается указанного класса среды выполнения.  
  
 `arg3`  
 Аргумент 3, передаваемое указанного класса среды выполнения.  
  
 `arg4`  
 Аргумент 4, который передается указанного класса среды выполнения.  
  
 `arg5`  
 Аргумент 5, который передается указанного класса среды выполнения.  
  
 `arg6`  
 Аргумент 6, передаваемое указанного класса среды выполнения.  
  
 `arg7`  
 Аргумент 7, который передается указанного класса среды выполнения.  
  
 `arg8`  
 Аргумент 8, который передается указанного класса среды выполнения.  
  
 `arg9`  
 Аргумент 9, передаваемое указанного класса среды выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Объект `ComPtr<T>` в случае успешного завершения операции; в противном случае — значение `nullptr`.  
  
## <a name="remarks"></a>Примечания  
 В разделе [как: непосредственно создать экземпляр компонентов WRL](../windows/how-to-instantiate-wrl-components-directly.md) для различия между данной функции и [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)и примеры.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)