---
title: 'Конструктор Module::genericreleasenotifier:: genericreleasenotifier | Документация Майкрософт'
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
ms.openlocfilehash: b0683220710a62c8583fa95fbfe3221ae93307eb
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603941"
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Конструктор Module::GenericReleaseNotifier::GenericReleaseNotifier
Инициализирует новый экземпляр класса **Module::GenericReleaseNotifier** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
### <a name="parameters"></a>Параметры  
 *обратный вызов*  
 Лямбда-выражения, функтором или обработчик событий указателя на функцию, который может быть вызван с помощью функции оператор «скобки» (`()`).  
  
 *release*  
 Укажите **true** для включения вызова базового [модуль:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) метода; в противном случае укажите **false**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс Module::GenericReleaseNotifier](../windows/module-genericreleasenotifier-class.md)