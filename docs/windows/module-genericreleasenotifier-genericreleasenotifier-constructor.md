---
title: 'Конструктор Module::genericreleasenotifier:: genericreleasenotifier | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb07c7f53e27e380ba5775369611299cad0f60d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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