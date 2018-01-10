---
title: "Сохранение отложенно загружаемых импортированных элементов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3800d4863bc1aa3e3c847ff0cea886be2fede985
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dumping-delay-loaded-imports"></a>Сохранение отложенно загружаемых импортированных элементов
Импорты, загружаемые с задержкой можно сохранять с помощью [dumpbin/Imports](../../build/reference/imports-dumpbin.md) и отображаются сведения немного отличается от обычных импортируемых элементов. Они находятся в отдельном разделе/Imports формирование дампа и явно помечены как импорты, загружаемые с задержкой. Если существует выгрузить сведений, представленных на рисунке, указывается. Если имеется информация о привязке, отметки даты и времени целевого DLL указан вместе с связанные адреса Импортируемые пространства имен.  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)