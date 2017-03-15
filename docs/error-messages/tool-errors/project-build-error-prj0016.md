---
title: "Ошибка построения проекта PRJ0016 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0016"
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка построения проекта PRJ0016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Параметры безопасности пользователи не позволяют создать проект.Данные параметры необходимы для сборки.  
  
 Пользователь вошел в систему без разрешений на создание процессов с использованием процесса.  Необходимо изменить уровни разрешения для этой учетной записи пользователя или связаться с администратором.  
  
 Эта ошибка также может возникать, если задан следующий раздел реестра:  
  
 \\\\HKCU\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\Explorer\\RestrictRun  
  
 Для устранения этой ошибки следует удалить раздел RestrictRun.  Если этот раздел реестра используется, следует добавить файл **vcspawn.exe** в список записей в этом разделе.  
  
 Другой причиной этой ошибкой может быть то, что в параметрах политики в разделе реестра HKEY\_CURRENT\_USER\\Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\RestrictRun файл VCSpawn.exe не включен как допустимая для этой учетной записи пользователя программа Windows.  
  
 Дополнительные сведения см. в разделах:  
  
-   Статья базы знаний 324153, доступная на [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Использование системных параметров политики](http://msdn.microsoft.com/library/aa372139), раздел "Запуск только допустимых приложений Windows".