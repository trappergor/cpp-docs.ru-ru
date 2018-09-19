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
ms.openlocfilehash: c6604bc0bf27b3d0192f602c4df88e5f01e4a161
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135962"
---
# <a name="project-build-error-prj0016"></a>Ошибка построения проекта PRJ0016

Параметры безопасности пользователя не позволяют процессу создания. Эти параметры необходимы для сборки.

Вы вошли качестве пользователя, который не имеет разрешений на создание процессов с помощью процесса. Необходимо изменить уровень разрешений для этой учетной записи пользователя или обратитесь к администратору учетной записи.

Эта ошибка также может возникнуть, если задано значение следующего раздела реестра:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Чтобы устранить эту ошибку, удалите раздел RestrictRun. Этот раздел реестра при необходимости, добавить **vcspawn.exe** в список записей в ключе.

Другой причиной этой ошибки является то, что параметры политики не включает VCSpawn.exe в разделе реестра HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun как разрешенные программа окно для этой учетной записи пользователя.

Дополнительные сведения см. в разделе:

- Статье базы знаний 324153, доступном на [ http://support.microsoft.com/default.aspx?scid=kb; en-us; 324153](http://support.microsoft.com/default.aspx?scid=kb;en-us;324153).

- [Использование системных параметров политики](https://msdn.microsoft.com/library/aa372139), раздел «Запуск только допустимых приложений Windows».