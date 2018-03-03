---
title: "Ошибка компилятора C3505 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3505
dev_langs:
- C++
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7b13350ea7a2ffaf232e990bd3ade42d0c44a6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3505"></a>Ошибка компилятора C3505

> не удается загрузить библиотеку типов "*guid*"  
  
C3505 может возникать, если вы используете 32-разрядные, размещенные x86 кросс компилятор для 64-разрядных систем, x64 целевых объектов на 64-разрядном компьютере, так как компилятор запускается в эмуляторе WOW64 и можно только считывать из 32-разрядный куст реестра.  
  
Можно устранить эту ошибку путем построения 32-разрядных и 64-разрядные версии библиотеки типов, которую вы пытаетесь импортировать и зарегистрируйте их обоих.  Или можно использовать собственный 64-разрядного компилятора, которой требуется изменить ваш **каталоги VC ++** свойство в интегрированной среде разработки, чтобы она указывала на 64-разрядный компилятор.  
  
Дополнительные сведения см. в следующих разделах:  
  
-   [Практическое руководство. Использование набора 64-разрядных инструментов Visual C++ в командной строке](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [Практическое руководство. Настройка проектов Visual C++ для 64-разрядных платформ с архитектурой x64](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)