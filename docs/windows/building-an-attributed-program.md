---
title: Сборка Атрибутированной программы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d87f95b456e3f99598f48e6ffa8ad29806aa168
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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