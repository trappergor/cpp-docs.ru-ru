---
title: Функция CreateClassFactory | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
dev_langs:
- C++
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ff853fce39b2052b82df921bf6743b0db361408c
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461329"
---
# <a name="createclassfactory-function"></a>CreateClassFactory - функция
Создает фабрику, которая создает экземпляры указанного класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename Factory>  
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(  
   _In_ unsigned int *flags,   
   _In_ const CreatorMap* entry,   
   REFIID riid,   
   _Outptr_ IUnknown **ppFactory  
) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 *flags*  
 Сочетание одного или нескольких [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значений перечисления.  
  
 *entry*  
 Указатель на [CreatorMap](../windows/creatormap-structure.md) , содержащий инициализации и регистрации сведений о параметрах *riid*.  
  
 *riid*  
 Ссылка на идентификатор интерфейса.  
  
 *ppFactory*  
 Если эта операция завершается успешно, указатель на фабрику класса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Ошибка assert создается в том случае, если параметр шаблона *фабрики* не является производным от интерфейса `IClassFactory`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)