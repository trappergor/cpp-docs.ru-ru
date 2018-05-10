---
title: Обратная совместимость | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- CRT, compatibility
- backward compatibility, C run-time libraries
- compatibility, C run-time libraries
- backward compatibility
ms.assetid: cc3175cf-97fd-492f-b329-5791aea63090
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9a04dec046435478ca621ad8f5e2e3c4323f3e2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="backward-compatibility"></a>Обратная совместимость
Для обеспечения совместимости между версиями продукта библиотека OLDNAMES.LIB сопоставляет старые имена с новыми именами. Например, `open` сопоставляется с `_open`. Явно выполнять компоновку с OLDNAMES.LIB необходимо только при компиляции со следующими параметрами командной строки:  
  
-   `/Zl` (опустить имя библиотеки по умолчанию из объектного файла) и `/Ze` (по умолчанию — использовать расширения Microsoft)  
  
-   `/link` (управление компоновщиком), `/NOD` (отключить поиск библиотеки по умолчанию) и `/Ze`  
  
 Дополнительные сведения о параметрах компилятора командной строки см. в [справочнике по компилятору](../build/reference/compiler-options.md).  
  
## <a name="see-also"></a>См. также  
 [Совместимость](../c-runtime-library/compatibility.md)