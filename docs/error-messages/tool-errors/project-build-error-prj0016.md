---
title: "Ошибка построения проекта PRJ0016 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PRJ0016
dev_langs: C++
helpviewer_keywords: PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9aa96ec353dbe236744a6a9baa5ad18ff25451d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="project-build-error-prj0016"></a>Ошибка построения проекта PRJ0016
Параметры безопасности пользователя не процесс создается. Эти параметры необходимы для сборки.  
  
 Вы вошли как пользователь не имеет разрешений на создание процессов с помощью процесса. Изменение уровней разрешений для этой учетной записи пользователя или обратитесь к администратору учетной записи.  
  
 Эта ошибка также может возникнуть, если значение следующего раздела реестра:  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 Чтобы устранить эту ошибку, удалите раздел RestrictRun. При необходимости этот раздел реестра, добавление **vcspawn.exe** к списку записей в разделе.  
  
 Другой причиной этой ошибки является, параметры политики не содержит VCSpawn.exe раздела реестра HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun как разрешенные программа окна для этой учетной записи пользователя.  
  
 Дополнительные сведения см. в разделе:  
  
-   Статья базы знаний 324153, доступном на [http://support.microsoft.com/default.aspx?scid=kb;en-us;324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Использование системных параметров политики](http://msdn.microsoft.com/library/aa372139), раздел «Запуск только допустимых приложений Windows».