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
ms.openlocfilehash: ceb004cba243d6e2e9c44aadcaa40670ef7a0bbb
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890261"
---
# <a name="project-build-error-prj0016"></a>Ошибка построения проекта PRJ0016

Параметры безопасности пользователя не позволяют процессу создания. Эти параметры необходимы для сборки.

Вы вошли качестве пользователя, который не имеет разрешений на создание процессов с помощью процесса. Необходимо изменить уровень разрешений для этой учетной записи пользователя или обратитесь к администратору учетной записи.

Эта ошибка также может возникнуть, если задано значение следующего раздела реестра:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Чтобы устранить эту ошибку, удалите раздел RestrictRun. Этот раздел реестра при необходимости, добавить **vcspawn.exe** в список записей в ключе.

Другой причиной этой ошибки является то, что параметры политики не включает VCSpawn.exe в разделе реестра HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun как разрешенные программа окно для этой учетной записи пользователя.

Дополнительные сведения см. в разделе [использование системных параметров политики](https://msdn.microsoft.com/library/aa372139), в разделе «Запуск только допустимых приложений Windows».