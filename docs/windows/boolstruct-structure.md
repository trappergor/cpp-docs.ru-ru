---
title: "Структура BoolStruct | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::BoolStruct
dev_langs: C++
helpviewer_keywords: BoolStruct structure
ms.assetid: 666eae78-e81d-4fb7-a9e4-1ba617d6d4cd
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7daa7527c8eea2cfca3b8933b9c3e1f042883e2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="boolstruct-structure"></a>BoolStruct - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct BoolStruct;  
```  
  
## <a name="remarks"></a>Примечания  
 Структура BoolStruct определяет, ли объект ComPtr управление временем существования объекта интерфейса. BoolStruct используется внутренним образом [BoolType()](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md) оператор.  
  
## <a name="members"></a>Участники  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Элемент данных BoolStruct::Member](../windows/boolstruct-member-data-member.md)|Указывает, что [ComPtr](../windows/comptr-class.md) является, или не, управление временем существования объектов интерфейса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BoolStruct`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)   
 [Оператор ComPtr::operator Microsoft::WRL::Details::BoolType](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)