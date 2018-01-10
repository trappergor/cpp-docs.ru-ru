---
title: "Создание манифеста в командной строке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- manifests [C++]
- manifest tool (mt.exe)
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ba88017e0003c7a552c985516dba9a6254317a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="manifest-generation-at-the-command-line"></a>Создание манифеста в командной строке
При построении приложений C/C++ из командной строки с помощью nmake или аналогичных инструментов, манифест создается после компоновщик обработает все файлы объектов и сборки конечный двоичный файл. Компоновщик собирает информацию о сборке хранятся в файлах объектов и объединяет эту информацию в конечный файл манифеста. По умолчанию компоновщик создает файл с именем < имя_двоичного_файла >. \<расширение > .manifest для описания в конечный двоичный файл. Компоновщик не встраивает файл манифеста в двоичный файл и может создать только из внешнего файла манифеста. Существует несколько способов для внедрения манифеста в конечный двоичный файл, например с помощью [инструмента манифеста (mt.exe)](http://msdn.microsoft.com/library/aa375649) или путем компиляции манифеста в файл ресурсов. Очень важно следует помнить, определенные правила для учитываться при внедрении манифеста в конечный двоичный файл, чтобы включить возможности, такие как инкрементная компоновка, подписывание, редактирование и продолжение. Эти и другие возможности описаны в [как: внедрить манифест в C/C++ приложения](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md) при построении в командной строке.  
  
## <a name="see-also"></a>См. также  
 [Манифесты](http://msdn.microsoft.com/library/aa375365)   
 [/ INCREMENTAL (инкрементная компоновка)](../build/reference/incremental-link-incrementally.md)   
 [Сборки со строгими именами (подписывание сборок) (C + +/ CLI)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [Изменить и продолжить](/visualstudio/debugger/edit-and-continue)   
 [Основные сведения о создании манифестов для программ на C/C++](../build/understanding-manifest-generation-for-c-cpp-programs.md)