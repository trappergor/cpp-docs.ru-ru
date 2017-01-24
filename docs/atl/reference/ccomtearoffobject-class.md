---
title: "CComTearOffObject Class | Microsoft Docs"
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
  - "ATL::CComTearOffObject<Base>"
  - "ATL::CComTearOffObject"
  - "ATL.CComTearOffObject"
  - "ATL.CComTearOffObject<Base>"
  - "CComTearOffObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComTearOffObject class"
  - "tear-off interfaces"
  - "tear-off interfaces, ATL - библиотека"
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс реализует интерфейс перемещаемый.  
  
## Синтаксис  
  
```  
  
      template<  
   class Base   
>  
class CComTearOffObject :  
   public Base  
```  
  
#### Параметры  
 `Base`  
 Перемещаемый собственный класс, производный от `CComTearOffObjectBase` и интерфейсы требуется пользовательский перемещаемый объект к поддержке.  
  
 Библиотеки ATL реализует его перемещаемые интерфейсы в шагах 2 — методы `CComTearOffObjectBase` обрабатывают счетчика ссылок и `QueryInterface`, пока `CComTearOffObject` реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComTearOffObject::CComTearOffObject](../Topic/CComTearOffObject::CComTearOffObject.md)|Конструктор.|  
|[CComTearOffObject::~CComTearOffObject](../Topic/CComTearOffObject::~CComTearOffObject.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComTearOffObject::AddRef](../Topic/CComTearOffObject::AddRef.md)|Увеличивает счетчик ссылок для объекта `CComTearOffObject`.|  
|[CComTearOffObject::QueryInterface](../Topic/CComTearOffObject::QueryInterface.md)|Возвращает указатель на запрашиваемый интерфейс на вашем перемещаемом классе или классе владелец.|  
|[CComTearOffObject::Release](../Topic/CComTearOffObject::Release.md)|Уменьшает счетчик ссылок для объекта `CComTearOffObject` и удаляет его.|  
  
### Методы CComTearOffObjectBase  
  
|||  
|-|-|  
|[CComTearOffObjectBase](../Topic/CComTearOffObject::CComTearOffObjectBase.md)|Конструктор.|  
  
### Элементы данных CComTearOffObjectBase  
  
|||  
|-|-|  
|[m\_pOwner](../Topic/CComTearOffObject::m_pOwner.md)|Указатель на `CComObject`, унаследованный от класса владелец.|  
  
## Заметки  
 Перемещаемый `CComTearOffObject` реализует интерфейс как отдельный объект, который создается только в том случае, если запрашивается интерфейс.  Перемещаемое удалено при его значение счетчика ссылок равно нулю.  Обычно при построении перемещаемый интерфейс для интерфейса, который редко используется, поскольку использование перемещаемое сохраняет указатель vtable во всех экземплярах основного объекта.  
  
 Необходимо создать класс, реализующий перемещаемое из `CComTearOffObjectBase` и каким из этих величин интерфейсам требуется пользовательский перемещаемый объект к поддержке.  `CComTearOffObjectBase` в классе templatized владелец и модели потока.  Класс владельцем класс объекта, для которого приведена перемещаемое.  Если не указать модель потока, то по умолчанию используется модель потока.  
  
 Необходимо создать сопоставление модели COM для перемещаемого класса.  Когда создает библиотеки ATL перемещаемое, он создает **CComTearOffObject\<CYourTearOffClass\>** или **CComCachedTearOffObject\<CYourTearOffClass\>**.  
  
 Например, в образце BEEPER, класс `CBeeper2` перемещаемый класс и класс `CBeeper` класс владелец:  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/CPP/ccomtearoffobject-class_1.h)]  
  
## Иерархия наследования  
 `Base`  
  
 `CComTearOffObject`  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComCachedTearOffObject Class](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)