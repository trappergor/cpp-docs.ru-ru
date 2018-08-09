---
title: Класс Module::MethodReleaseNotifier | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier class
ms.assetid: 5c2902be-964b-488f-9f1c-adf504995cbc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80b2653128415cfd847db5b9592df116ffd0d470
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014316"
---
# <a name="modulemethodreleasenotifier-class"></a>Класс Module::MethodReleaseNotifier
Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий заданного объекта и ее члена указатель на метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Тип объекта, функция-член которого является обработчиком событий.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор Module::MethodReleaseNotifier::MethodReleaseNotifier](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Инициализирует новый экземпляр класса **Module::MethodReleaseNotifier** класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод Module::MethodReleaseNotifier::Invoke](../windows/module-methodreleasenotifier-invoke-method.md)|Вызывает обработчик событий, связанный с текущим **Module::MethodReleaseNotifier** объекта.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание:|  
|----------|-----------------|  
|[Элемент данных Module::MethodReleaseNotifier::method_](../windows/module-methodreleasenotifier-method-data-member.md)|Содержит указатель на обработчик событий для текущего **Module::MethodReleaseNotifier** объекта.|  
|[Элемент данных Module::MethodReleaseNotifier::object_](../windows/module-methodreleasenotifier-object-data-member.md)|Содержит указатель на объект, функция-член которого является обработчиком событий для текущего **Module::MethodReleaseNotifier** объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)