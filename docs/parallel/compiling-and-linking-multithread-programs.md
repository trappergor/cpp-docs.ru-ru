---
title: Компиляция и компоновка многопоточных программ | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5df81fa3d47005fc80bdb3b1c78cba050775cda6
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2018
ms.locfileid: "42540280"
---
# <a name="compiling-and-linking-multithread-programs"></a>Компиляция и компоновка многопоточных программ
В программе Bounce.c впервые появился в [Пример многопоточной программы на C](../parallel/sample-multithread-c-program.md).  
  
Скомпилированные программы многопоточных по умолчанию.  
  
### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Для компиляции и компоновки многопоточной программы Bounce.c в среде разработки  
  
1.  В меню **Файл** последовательно выберите пункты **Создать**и **Проект**.  
  
2.  В **типы проектов** панели щелкните **Win32**.  
  
3.  В **шаблоны** панели щелкните **консольное приложение Win32**, а затем введите имя проекта.  
  
4.  Добавьте файл, содержащий исходный код C для проекта.  
  
5.  На **построения** меню, постройте проект, нажав кнопку **построения** команды.  
  
### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Для компиляции и компоновки многопоточной программы Bounce.c из командной строки  
  
1.  Компиляции и компоновки программы:  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## <a name="see-also"></a>См. также

[Реализация многопоточности на языке C с помощью функций Win32](../parallel/multithreading-with-c-and-win32.md)