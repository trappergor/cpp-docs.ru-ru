---
title: "Конструктор Module::genericreleasenotifier:: genericreleasenotifier | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5f6f656ff1908dc215efb1fc322b348618a236d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Конструктор Module::GenericReleaseNotifier::GenericReleaseNotifier
Инициализирует новый экземпляр класса Module::GenericReleaseNotifier.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### <a name="parameters"></a>Параметры  
 `callback`  
 Лямбда-выражения, функтором или обработчик событий указателя на функцию, который может быть вызван с функция оператор «скобки» (`()`).  
  
 `release`  
 Укажите `true` для включения вызов базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) метода; в противном случае укажите `false`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс Module::GenericReleaseNotifier](../windows/module-genericreleasenotifier-class.md)