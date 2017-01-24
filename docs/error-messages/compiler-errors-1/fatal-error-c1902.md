---
title: "Неустранимая ошибка C1902 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1902"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1902"
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1902
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

несоответствие диспетчера базы данных программы; проверьте установку  
  
 Файл базы данных программы \(PDB\) был создан с использованием более поздней версии mspdb *XX*.dll одного компилятор найден в системе.  Эта ошибка обычно указывает на то, что файл mspdbsrv.exe или mspdbcore.dll отсутствует или не имеют разные версии mspdb *XX*.dll. \(Заполнитель *XX* в изменениях имени файла mspdb *XX*.dll с каждым новым выпуском продукта.  Например, в [!INCLUDE[vsprvslong](../../error-messages/compiler-errors-1/includes/vsprvslong_md.md)] этот файл называется mspdb80.dll.  
  
 Убедитесь, что версии сопоставление mspdbsrv.exe, mspdbcore.dll и mspdb *XX*.dll установлено в системе.  Убедитесь, что в каталог, содержащий инструменты компиляции и компоновки для целевой платформы, не были скопированы файлы с несовпадающими версиями.  Например, файлы могли быть скопированы для того, чтобы вызывать компилятор или компоновщик из командной строки без настройки переменной окружения **PATH**.