---
title: "Конструктор Module::methodreleasenotifier:: methodreleasenotifier | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs: C++
helpviewer_keywords: MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 045dd8dd0dbee58c0feea33bc7ce4f6cea30e591
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Конструктор Module::MethodReleaseNotifier::MethodReleaseNotifier
Инициализирует новый экземпляр класса Module::MethodReleaseNotifier.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### <a name="parameters"></a>Параметры  
 `object`  
 Объект, функция-член которого является обработчиком событий.  
  
 `method`  
 Функция-член параметра `object` , обработчик событий.  
  
 `release`  
 Укажите `true` для включения вызов базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) метода; в противном случае укажите `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс Module::MethodReleaseNotifier](../windows/module-methodreleasenotifier-class.md)