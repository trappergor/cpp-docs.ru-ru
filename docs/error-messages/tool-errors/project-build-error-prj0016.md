---
title: Ошибка построения проекта PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: ada89b074fd8e0c2bfc75ba833e9c5966a145312
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616870"
---
# <a name="project-build-error-prj0016"></a>Ошибка построения проекта PRJ0016

Параметры безопасности пользователя не позволяют процессу создания. Эти параметры необходимы для сборки.

Вы вошли качестве пользователя, который не имеет разрешений на создание процессов с помощью процесса. Необходимо изменить уровень разрешений для этой учетной записи пользователя или обратитесь к администратору учетной записи.

Эта ошибка также может возникнуть, если задано значение следующего раздела реестра:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Чтобы устранить эту ошибку, удалите раздел RestrictRun. Этот раздел реестра при необходимости, добавить **vcspawn.exe** в список записей в ключе.

Другой причиной этой ошибки является то, что параметры политики не включает VCSpawn.exe в разделе реестра HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun как разрешенные программа окно для этой учетной записи пользователя.

Дополнительные сведения см. в разделе [использование системных параметров политики](https://msdn.microsoft.com/library/aa372139), в разделе «Запуск только допустимых приложений Windows».