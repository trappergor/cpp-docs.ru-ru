---
title: "Конструктор Module::releasenotifier:: releasenotifier | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier
dev_langs: C++
helpviewer_keywords: ReleaseNotifier, constructor
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a82f8d2f753325c123d78cacbb10fdc25449fd51
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="modulereleasenotifierreleasenotifier-constructor"></a>Конструктор Module::ReleaseNotifier::ReleaseNotifier
Инициализирует новый экземпляр класса Module::ReleaseNotifier.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `release`  
 `true`Удаление этого экземпляра при вызове метода Release; `false` не удалить этот экземпляр.  
  
## <a name="exceptions"></a>Исключения  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс Module::ReleaseNotifier](../windows/module-releasenotifier-class.md)