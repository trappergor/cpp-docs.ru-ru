---
title: "Структура библиотеки | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- libraries, structure
ms.assetid: a5fda8e8-4a1b-4499-9095-0df935262ce4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1630636b0de552712f67bc43b5182f991b10ef0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="structure-of-a-library"></a>Структура библиотеки
Библиотека содержит объекты COFF. Объекты в библиотеке содержат функции и данные, которые могут быть внешние ссылки другими объектами в программе. Объект в библиотеке, иногда называют члена библиотеки.  
  
 Дополнительные сведения о содержимом библиотеки можно получить, запустив средство DUMPBIN с параметром/LINKERMEMBER. Дополнительные сведения об этом параметре см. в разделе [Справочник DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о LIB](../../build/reference/overview-of-lib.md)