---
title: Сохранение отложенно загружаемых импортированных элементов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delay-loaded imports, dumping
- imports (delay-loaded)
- delay-loaded imports
ms.assetid: f766acf4-9df8-4b85-8cf6-0be3ffc4c124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13f832f0ea7aaf7b766141ce7df4f83f21e1cdca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372871"
---
# <a name="dumping-delay-loaded-imports"></a>Сохранение отложенно загружаемых импортированных элементов
Импорты, загружаемые с задержкой можно сохранять с помощью [dumpbin/Imports](../../build/reference/imports-dumpbin.md) и отображаются сведения немного отличается от обычных импортируемых элементов. Они находятся в отдельном разделе/Imports формирование дампа и явно помечены как импорты, загружаемые с задержкой. Если существует выгрузить сведений, представленных на рисунке, указывается. Если имеется информация о привязке, отметки даты и времени целевого DLL указан вместе с связанные адреса Импортируемые пространства имен.  
  
## <a name="see-also"></a>См. также  
 [Поддержка компоновщика для библиотек DLL с отложенной загрузкой](../../build/reference/linker-support-for-delay-loaded-dlls.md)