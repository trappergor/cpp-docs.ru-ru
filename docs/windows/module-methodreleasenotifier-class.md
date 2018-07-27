---
title: Класс Module::MethodReleaseNotifier | Документы Microsoft
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
ms.openlocfilehash: 217e58f73130922d45f0d303e1e91858e8c2272f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880831"
---
# <a name="modulemethodreleasenotifier-class"></a>Класс Module::MethodReleaseNotifier
Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается объектом и его элементом указателя для метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T>  
class MethodReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта, функция-член которого является обработчиком событий.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор Module::MethodReleaseNotifier::MethodReleaseNotifier](../windows/module-methodreleasenotifier-methodreleasenotifier-constructor.md)|Инициализирует новый экземпляр класса Module::MethodReleaseNotifier.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Module::MethodReleaseNotifier::Invoke](../windows/module-methodreleasenotifier-invoke-method.md)|Вызывает обработчик событий, связанных с текущего объекта Module::MethodReleaseNotifier.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|name|Описание|  
|----------|-----------------|  
|[Элемент данных Module::MethodReleaseNotifier::method_](../windows/module-methodreleasenotifier-method-data-member.md)|Содержит указатель на обработчик событий для текущего объекта Module::MethodReleaseNotifier.|  
|[Элемент данных Module::MethodReleaseNotifier::object_](../windows/module-methodreleasenotifier-object-data-member.md)|Содержит указатель на объект, функция-член которого является обработчиком событий для текущего объекта Module::MethodReleaseNotifier.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ReleaseNotifier`  
  
 `MethodReleaseNotifier`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)