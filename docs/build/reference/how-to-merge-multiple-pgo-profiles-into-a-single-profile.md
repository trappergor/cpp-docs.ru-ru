---
title: "Как: слияние нескольких профилей PGO в единый профиль | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 880e9fbba7852a9a7919e73f80b73e34394cd037
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>Практическое руководство. Слияние нескольких профилей PGO в единый профиль
Профильная оптимизация (PGO) является мощный инструмент для создания оптимизированного двоичного кода, в зависимости от варианта, который выполняется профилирование. Но что делать, если у вас есть приложение, имеет несколько важных различных сценариев; как создать единый профиль, профильной Оптимизации можно использовать из нескольких различных сценариях В Visual Studio диспетчер профильной Оптимизации Pgomgr.exe, выполняет это задание.  
  
 Для объединения профилей используется синтаксис:  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 где `num` — необязательный весовой коэффициент, используемый при слиянии. Весовые коэффициенты обычно используются при наличии скриптов, которые являются более важной, чем другие, или если существуют сценарии, которые должны выполняться несколько раз.  
  
> [!NOTE]
>  Диспетчер профильной Оптимизации не будут работать с данными устаревших профиля. Чтобы объединить PGC-файл в PGD-файл, PGC-файл должен быть создан путем исполняемого файла, который был создан в одном вызове компоновки, что и PGD-файл.  
  
## <a name="example"></a>Пример  
 В этом примере диспетчер профильной Оптимизации добавит файл pgcFile.pgc в файл pgdFile.pgd шесть раз.  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Пример  
 В этом примере диспетчер профильной Оптимизации добавит pgcFile1.pgc и pgcFile2.pgc файл pgdFile.pgd дважды для каждого PGC-файл.  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>Пример  
 Если при запуске диспетчера профильной Оптимизации PGC-файл, он выполняет поиск локальный каталог для всех файлов, имеющих то же имя, что PGD-файл, добавленным с восклицательным знаком (!) и произвольными символами. Если локальный каталог содержит файлы test.pgd, test!1.pgc, test2.pgc и test!hello.pgc следующая команда запускается из локального каталога, затем test!1.pgc и test!hello.pgc будут объединены в test.pgd.  
  
```  
pgomgr /merge test.pgd  
```  
  
## <a name="see-also"></a>См. также  
 [Профильная оптимизация](../../build/reference/profile-guided-optimizations.md)