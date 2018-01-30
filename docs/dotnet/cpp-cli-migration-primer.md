---
title: "C + +/ CLI Основы миграции | Документы Microsoft"
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
- C++/CLI Version 2
- upgrading Visual C++ applications, Managed Extensions for C++ to Visual C++ 2005 syntax
- migration [C++], C++/CLI Version 2
- Managed Extensions for C++, upgrading syntax
- C++/CLI Version 2, managed extensions
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 17474b347a6daf2d477a6ed731e13db86e068b05
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2018
---
# <a name="ccli-migration-primer"></a>Основы миграции C++/CLI
Это руководство по переносу ваших программ Visual C++ из управляемых расширений для C++ к Visual C++. 
  
 C + +/ CLI является расширением парадигмы программирования динамических компонентов, для стандартного языка C++ стандарта ISO. Новый язык предлагает ряд значительные усовершенствования, внесенные через управляемых расширений. Этот раздел предоставляет нумерованный перечень управляемых расширений функций языка C++ и их соответствие для Visual C++, где такое сопоставление существует и указывает таких конструкций, для которых не существует сопоставления.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Обзор изменений (C++/CLI)](../dotnet/outline-of-changes-cpp-cli.md)  
 Высокоуровневый обзор краткий обзор изменений по пяти основным категориям.  
  
 [Ключевые слова языка (C++/CLI)](../dotnet/language-keywords-cpp-cli.md)  
 Рассматриваются изменения в ключевых словах языка, включая удаление двойной знак подчеркивания и появлением контекстные и составные ключевые слова.  
  
 [Управляемые типы (C + +/ CL)](../dotnet/managed-types-cpp-cl.md)  
 Рассматриваются изменения в объявлении из системы общих типов (CTS) - синтаксисе включает изменения в объявлении классов, массивов (включая массивы параметров), перечислений и т. д.  
  
 [Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 Описание изменений, касающихся членов класса, такие как скалярные свойства, свойства индекса, операторы, делегаты и события.  
  
 [Типы значений и их режимы работы (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Основное внимание уделяется типов значений и нового семейства внутренних и закрепляющих указателей. В нем также описывается ряд существенных изменений в семантике такие как введение неявная упаковка-преобразование, неизменность упакованных типов значений и удаление поддержки конструкторы по умолчанию внутри классов значений.  
  
 [Общие изменения в языке (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)  
 Подробно рассматриваются изменения, такие как поддержка нотация приведения типов строка литерала поведение, а также изменения в семантике между ISO C++ и C + +/ CLI.  
  
## <a name="see-also"></a>См. также  
 [Смешанные (собственные и управляемые) сборки](../dotnet/mixed-native-and-managed-assemblies.md)   
 [Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)