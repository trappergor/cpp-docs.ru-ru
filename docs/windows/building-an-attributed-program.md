---
title: "Сборка Атрибутированной программы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tlb files
- MIDL
- MIDL, linker output
- IDL files
- tlb files, building attributed programs
- .tlb files, building attributed programs
- IDL files, building
- attributes [C++], building type libraries and .idl files
- .tlb files
- .idl files, building
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3e39bbd2b630d35942c1c5107041b2fbadf7549
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="building-an-attributed-program"></a>Сборка атрибутированной программы
После помещения атрибутов Visual C++ в исходный код, вы можете компилятор Visual C++ для создания файла библиотеки и .idl тип для вас. Компоновщик следующие параметры помогают построить файлы с расширением TLB и .idl:  
  
-   [/ IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [/ IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [/ MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [/ TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 Некоторые проекты содержат несколько независимых .idl файлов. Эти значения используются для создания двух или более TLB-файлы и их привязки в блоке ресурсов. Этот сценарий не поддерживается в Visual C++.  
  
 Кроме того компоновщик Visual C++ будет выводить все сведения атрибута, связанного с IDL в единый файл MIDL. Будет невозможно создавать два библиотеки типов из одного проекта.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../windows/attributed-programming-concepts.md)