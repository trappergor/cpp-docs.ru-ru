---
title: "Структура библиотеки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 875dddb961b18378029de08582e728ad626be948
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="structure-of-a-library"></a>Структура библиотеки
Библиотека содержит объекты COFF. Объекты в библиотеке содержат функции и данные, которые могут быть внешние ссылки другими объектами в программе. Объект в библиотеке, иногда называют члена библиотеки.  
  
 Дополнительные сведения о содержимом библиотеки можно получить, запустив средство DUMPBIN с параметром/LINKERMEMBER. Дополнительные сведения об этом параметре см. в разделе [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о LIB](../../build/reference/overview-of-lib.md)