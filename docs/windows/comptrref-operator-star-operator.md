---
title: Оператор ComPtrRef::operator * | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator*
dev_langs:
- C++
helpviewer_keywords:
- operator* operator
ms.assetid: 0287ca7a-4ce1-47f7-bab6-714fca3e04bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55d4fa6156c4ef2032111c0306c3cff8dce14059
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461456"
---
# <a name="comptrrefoperator-operator"></a>Оператор ComPtrRef::operator*
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
InterfaceType* operator *();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, представленный текущим **ComPtrRef** объекта.  
  
## <a name="remarks"></a>Примечания  
 Извлекает указатель на интерфейс, представленный текущим **ComPtrRef** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Comptrref-класс](../windows/comptrref-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)