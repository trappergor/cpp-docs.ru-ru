---
title: Элемент данных Creatormap::activationid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::activationId
dev_langs:
- C++
helpviewer_keywords:
- activationId data member
ms.assetid: 77518b76-6e6a-4b48-8e2e-a4c7c67769e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 70a331bbbf34a623b02e9d8bc9aa0b80fbee2216
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467135"
---
# <a name="creatormapactivationid-data-member"></a>Элемент данных CreatorMap::activationId
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
union {   
   const IID* clsid;  
   const wchar_t* (*getRuntimeName)();  
} activationId;  
```  
  
## <a name="parameters"></a>Параметры  
 *CLSID*  
 Идентификатор интерфейса.  
  
 *getRuntimeName*  
 Функция, которая извлекает имя объекта в среде выполнения Windows.  
  
## <a name="remarks"></a>Примечания  
 Представляет идентификатор объекта, который определен идентификатором класса классической модели COM или именем в среде выполнения Windows.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Creatormap-структура](../windows/creatormap-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)