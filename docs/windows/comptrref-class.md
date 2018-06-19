---
title: Класс ComPtrRef | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d961ed0a675927846788c013e61767f99b408c6b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871449"
---
# <a name="comptrref-class"></a>ComPtrRef - класс
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Объект [ComPtr\<T >](../windows/comptr-class.md) тип или тип, производный от него, а не просто интерфейс, представленный экземпляром ComPtr.  
  
## <a name="remarks"></a>Примечания  
 Представляет ссылку на объект ComPtr типа\<T >.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор ComPtrRef::ComPtrRef](../windows/comptrref-comptrref-constructor.md)|Инициализирует новый экземпляр класса ComPtrRef из заданного указателя с другим объектом ComPtrRef.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод ComPtrRef::GetAddressOf](../windows/comptrref-getaddressof-method.md)|Извлекает адрес указателя на интерфейс, представленный текущим объектом ComPtrRef.|  
|[Метод ComPtrRef::ReleaseAndGetAddressOf](../windows/comptrref-releaseandgetaddressof-method.md)|Удаляет текущий объект ComPtrRef и возвращает указатель на указатель на интерфейс, представленный объектом ComPtrRef.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор ComPtrRef::operator InterfaceType**](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Удаляет текущий объект ComPtrRef и возвращает указатель на указатель на интерфейс, представленный объектом ComPtrRef.|  
|[Оператор ComPtrRef::operator T*](../windows/comptrref-operator-t-star-operator.md)|Возвращает значение [ptr_](../windows/comptrrefbase-ptr-data-member.md) элемент данных текущим объектом ComPtrRef.|  
|[Оператор ComPtrRef::operator void**](../windows/comptrref-operator-void-star-star-operator.md)|Удаляет текущий объект ComPtrRef, приводит указатель на интерфейс, представленный объектом ComPtrRef как указатель в указатель to `void`и затем возвращает указатель приведения.|  
|[Оператор ComPtrRef::operator*](../windows/comptrref-operator-star-operator.md)|Извлекает указатель на интерфейс, представленный текущим объектом ComPtrRef.|  
|[Оператор ComPtrRef::operator==](../windows/comptrref-operator-equality-operator.md)|Указывает, равны ли два объекта ComPtrRef.|  
|[Оператор ComPtrRef::operator!=](../windows/comptrref-operator-inequality-operator.md)|Указывает на неравенство двух объектов ComPtrRef.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)