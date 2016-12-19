---
title: "Класс ModuleBase | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::ModuleBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ModuleBase - класс"
ms.assetid: edce7591-6893-46f7-94a7-382827775548
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс ModuleBase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ModuleBase;  
```  
  
## <a name="remarks"></a>Примечания  
 Представляет базовый класс для [модуля](../windows/module-class.md) классы.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор ModuleBase::ModuleBase](../windows/modulebase-modulebase-constructor.md)|Инициализирует новый экземпляр класса Module.|  
|[ModuleBase:: ~ ModuleBase деструктор](../windows/modulebase-tilde-modulebase-destructor.md)|Деинициализирует текущий экземпляр класса Module.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод ModuleBase::DecrementObjectCount](../Topic/ModuleBase::DecrementObjectCount%20Method.md)|При реализации уменьшает число объектов, отслеживаемых модулем.|  
|[Метод ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md)|При реализации увеличивает число объектов, отслеживаемых модулем.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ModuleBase`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)