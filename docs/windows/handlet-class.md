---
title: "Класс HandleT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs: C++
helpviewer_keywords: HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 293be59e15ca91254cad520a6d7fbf84410ed8e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="handlet-class"></a>HandleT - класс
Представляет дескриптор объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename HandleTraits  
>  
class HandleT;  
```  
  
#### <a name="parameters"></a>Параметры  
 `HandleTraits`  
 Экземпляр [HandleTraits](../windows/handletraits-structure.md) структура, которая определяет общие характеристики дескриптора.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`Traits`|Синоним для `HandleTraits`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор HandleT::HandleT](../windows/handlet-handlet-constructor.md)|Инициализирует новый экземпляр класса HandleT.|  
|[Деструктор HandleT::~HandleT](../windows/handlet-tilde-handlet-destructor.md)|Отменяет инициализацию экземпляра класса HandleT.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод HandleT::Attach](../windows/handlet-attach-method.md)|Связывает указанный дескриптор с текущего объекта HandleT.|  
|[Метод HandleT::Close](../windows/handlet-close-method.md)|Закрытие текущего объекта HandleT.|  
|[Метод HandleT::Detach](../windows/handlet-detach-method.md)|Отсоединяет текущий объект HandleT из его базового дескриптора.|  
|[Метод HandleT::Get](../windows/handlet-get-method.md)|Возвращает значение базового дескриптора.|  
|[Метод HandleT::IsValid](../windows/handlet-isvalid-method.md)|Указывает, представляет ли текущий объект HandleT дескриптор.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод HandleT::InternalClose](../windows/handlet-internalclose-method.md)|Закрытие текущего объекта HandleT.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Оператор HandleT::operator=](../windows/handlet-operator-assign-operator.md)|Перемещение текущего объекта HandleT значение указанного объекта HandleT.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных HandleT::handle_](../windows/handlet-handle-data-member.md)|Содержит дескриптор, который представлен объектом HandleT.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HandleT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)