---
title: "Ошибка BSCMAKE BK1517 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK1517"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1517"
ms.assetid: 24391f42-0a3e-40a9-9991-c8b9a6a7b1c7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка BSCMAKE BK1517
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

исходный SBR\-файл скомпилирован с параметрами \/Yc и \/Yu  
  
 SBR\-файл ссылается на себя.  Вероятно, он был перекомпилирован с параметром \/Yu после компиляции с параметром \/Yc.  Восстановите у исходного файла параметр компилятора \/Yc и выберите команду **Перестроить**, чтобы создать новые SBR\-файлы.  Не перекомпилируйте исходный файл с параметром \/Yu.