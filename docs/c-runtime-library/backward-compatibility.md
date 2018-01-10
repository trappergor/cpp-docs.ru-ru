---
title: "Обратная совместимость | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: c.programs
dev_langs: C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a8ffcc5ab1f50c474ed0ecf4d014419111682b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="backward-compatibility"></a>Обратная совместимость
Для обеспечения совместимости между версиями продукта библиотека OLDNAMES.LIB сопоставляет старые имена с новыми именами. Например, `open` сопоставляется с `_open`. Явно выполнять компоновку с OLDNAMES.LIB необходимо только при компиляции со следующими параметрами командной строки:  
  
-   `/Zl` (опустить имя библиотеки по умолчанию из объектного файла) и `/Ze` (по умолчанию — использовать расширения Microsoft)  
  
-   `/link` (управление компоновщиком), `/NOD` (отключить поиск библиотеки по умолчанию) и `/Ze`  
  
 Дополнительные сведения о параметрах компилятора командной строки см. в [справочнике по компилятору](../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>См. также  
 [Совместимость](../c-runtime-library/compatibility.md)