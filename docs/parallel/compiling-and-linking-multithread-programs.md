---
title: "Компиляция и компоновка многопоточных программ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- compiling multithreaded programs
- multithreading [C++], linking programs
- threading [C++], linking programs
- multithreading [C++], compiled programs
- threading [C++], compiled programs
- compiling source code [C++], multithread programs
- linking [C++], multithread programs
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0145c480d74cb1978c1b6caef65489eae96501c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiling-and-linking-multithread-programs"></a>Компиляция и компоновка многопоточных программ
Программа Bounce.c представлена [Пример многопоточной программы на языке C](../parallel/sample-multithread-c-program.md).  
  
 Скомпилированные программы многопоточных по умолчанию.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Компиляция и компоновка многопоточной программы Bounce.c в среде разработки  
  
1.  В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.  
  
2.  В **типы проектов** области, нажмите кнопку **Win32**.  
  
3.  В **шаблоны** области, нажмите кнопку **консольное приложение Win32**, а затем назовите проект.  
  
4.  Добавьте файл, содержащий исходный код C для проекта.  
  
5.  На **построения** меню, постройте проект, нажав кнопку **построения** команды.  
  
#### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Компиляция и компоновка многопоточной программы Bounce.c из командной строки  
  
1.  Компиляции и компоновки программы:  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## <a name="see-also"></a>См. также  
 [Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)