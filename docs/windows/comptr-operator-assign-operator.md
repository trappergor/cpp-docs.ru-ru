---
title: ComPtr::operator =-оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f4066db37de8a993802970784f09141352fef028
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871205"
---
# <a name="comptroperator-operator"></a>Оператор ComPtr::operator=
Присваивает значение текущему объекту ComPtr.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <typename U>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<class U>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `U`  
 Класс.  
  
 `other`  
 Указатель, ссылка или rvalue ссылаются на тип или другой объект ComPtr.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект ComPtr.  
  
## <a name="remarks"></a>Примечания  
 Первая версия этого оператора присваивает пустое значение текущему объекту ComPtr.  
  
 Во второй версии, если присваиваемый указатель интерфейса не совпадает с текущим указателем интерфейса ComPtr, второй указатель интерфейса присваивается текущему объекту ComPtr.  
  
 В третьей версии присваиваемый указатель интерфейса присваивается текущему объекту ComPtr.  
  
 В четвертой версии, если указатель интерфейса присваиваемого значения не совпадает с текущим указателем интерфейса ComPtr, второй указатель интерфейса присваивается текущему объекту ComPtr.  
  
 Пятая версия является оператором копирования; ссылка на объект ComPtr присваивается текущему объекту ComPtr.  
  
 Шестая версия является оператором копирования, использующим семантику перемещения; rvalue ссылается на объект ComPtr, если любой тип приводится статически, а затем присваивается текущему объекту ComPtr.  
  
 Седьмая версия является оператором копирования, использующим семантику перемещения; rvalue ссылается на объект ComPtr типа `U`, который приводится статически, а затем присваивается текущему объекту ComPtr.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)