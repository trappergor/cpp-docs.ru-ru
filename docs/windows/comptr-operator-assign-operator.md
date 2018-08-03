---
title: Оператор ComPtr::operator =-оператор | Документация Майкрософт
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
ms.openlocfilehash: fac3a845ea7c512f5a7ccffdabdf67ce26029ff8
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466167"
---
# <a name="comptroperator-operator"></a>Оператор ComPtr::operator=
Присваивает значение текущему **ComPtr**.  
  
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
 *U*  
 Класс.  
  
 *other*  
 Указатель, ссылку или ссылку rvalue на тип или другой **ComPtr**.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылку на текущий **ComPtr**.  
  
## <a name="remarks"></a>Примечания  
 Первая версия этого оператора присваивает пустое значение текущему **ComPtr**.  
  
 Во второй версии, если присваиваемый указатель интерфейса не совпадает с текущим **ComPtr** указатель на интерфейс, второй указатель интерфейса присваивается текущему **ComPtr**.  
  
 В третьей версии присваиваемый указатель интерфейса присваивается текущему **ComPtr**.  
  
 В четвертой версии, если указатель интерфейса присваиваемого значения не совпадает с текущим **ComPtr** указатель на интерфейс, второй указатель интерфейса присваивается текущему **ComPtr**.  
  
 Пятая версия является оператором копирования; ссылку на **ComPtr** назначается текущему **ComPtr**.  
  
 Шестая версия является оператором копирования, использующим перемещение семантику; ссылка rvalue на **ComPtr** Если любой тип приводится статически, а затем присваивается текущий **ComPtr**.  
  
 Седьмая версия является оператором копирования, использующим перемещение семантику; ссылка rvalue на **ComPtr** типа *U* является статическим затем приведение и назначена текущему **ComPtr**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)