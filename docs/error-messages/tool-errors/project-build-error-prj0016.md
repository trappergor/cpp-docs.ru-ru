---
title: Ошибка построения проекта PRJ0016 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- PRJ0016
dev_langs:
- C++
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c07de9e766b7c2126d0ce4c8d1daed631a8355c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194744"
---
# <a name="project-build-error-prj0016"></a>Ошибка построения проекта PRJ0016
Параметры безопасности пользователя не позволяют процессу создания. Эти параметры необходимы для сборки.  
  
 Вы вошли качестве пользователя, который не имеет разрешений на создание процессов с помощью процесса. Необходимо изменить уровень разрешений для этой учетной записи пользователя или обратитесь к администратору учетной записи.  
  
 Эта ошибка также может возникнуть, если задано значение следующего раздела реестра:  
  
 \\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun  
  
 Чтобы устранить эту ошибку, удалите раздел RestrictRun. Этот раздел реестра при необходимости, добавить **vcspawn.exe** в список записей в ключе.  
  
 Другой причиной этой ошибки является то, что параметры политики не включает VCSpawn.exe в разделе реестра HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun как разрешенные программа окно для этой учетной записи пользователя.  
  
 Дополнительные сведения см. в разделе:  
  
-   Статье базы знаний 324153, доступном на [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).  
  
-   [Использование системных параметров политики](https://msdn.microsoft.com/library/aa372139), раздел «Запуск только допустимых приложений Windows».