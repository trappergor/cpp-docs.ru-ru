---
title: "Класс ComPtrRefBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs: C++
helpviewer_keywords: ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c010b85095da67a91c0b4c1df6f3da7a4f677dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase - класс
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Объект [ComPtr\<T >](../windows/comptr-class.md) тип или тип, производный от него, а не просто интерфейс, представленный экземпляром ComPtr.  
  
## <a name="remarks"></a>Примечания  
 Представляет базовый класс для [ComPtrRef](../windows/comptrref-class.md) класса.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`InterfaceType`|Синоним для типа параметра шаблона `T`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор ComPtrRefBase::operator IInspectable**](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Приводит текущие [ptr_](../windows/comptrrefbase-ptr-data-member.md) данные-член к указателю к a указатель-интерфейс IInspectable.|  
|[Оператор ComPtrRefBase::operator IUnknown**](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Приводит текущие [ptr_](../windows/comptrrefbase-ptr-data-member.md) данные-член к указатель в a указатель интерфейса IUnknown.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных ComPtrRefBase::ptr_](../windows/comptrrefbase-ptr-data-member.md)|Указатель на тип, заданный текущим параметром шаблона.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)