---
title: "Класс CriticalSection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection class
ms.assetid: f2e0a024-71a3-4f6b-99ea-d93a4a608ac4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e2bf6e4728bac6622f9872ab939e084b14f49ae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="criticalsection-class"></a>CriticalSection - класс
Представляет объект критической секции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CriticalSection;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="constructor"></a>Конструктор  
  
|name|Описание:|  
|----------|-----------------|  
|[Конструктор CriticalSection::CriticalSection](../windows/criticalsection-criticalsection-constructor.md)|Инициализирует объект синхронизации, который похож на объекте mutex, но может использоваться только потоками одного процесса.|  
|[Деструктор CriticalSection::~CriticalSection](../windows/criticalsection-tilde-criticalsection-destructor.md)|Отменяет инициализацию и удаляет текущий объект CriticalSection.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод CriticalSection::TryLock](../windows/criticalsection-trylock-method.md)|Попытки ввода критической секции без блокировки. При успешном вызове вызывающий поток принимает право на владение критической секции.|  
|[Метод CriticalSection::Lock](../windows/criticalsection-lock-method.md)|Ожиданий владения объектом указанного критической секции. Эта функция возвращает при предоставлении владельцем вызывающего потока.|  
|[Метод CriticalSection::IsValid](../windows/criticalsection-isvalid-method.md)|Указывает, является ли допустимым текущую критическую секцию.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[Элемент данных CriticalSection::cs_](../windows/criticalsection-cs-data-member.md)|Объявляет член данных критической секции.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CriticalSection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)