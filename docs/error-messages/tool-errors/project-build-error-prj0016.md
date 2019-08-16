---
title: Ошибка построения проекта PRJ0016
ms.date: 11/04/2016
f1_keywords:
- PRJ0016
helpviewer_keywords:
- PRJ0016
ms.assetid: e9745336-883a-4c70-9c40-7753e02f0325
ms.openlocfilehash: 6733ef1f390f2ff377356dda3f7cd3ebfe10cc2b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509879"
---
# <a name="project-build-error-prj0016"></a>Ошибка построения проекта PRJ0016

Параметры безопасности пользователя препятствуют созданию процесса. Эти параметры необходимы для сборки.

Вы вошли в систему как пользователь, у которого нет разрешений на создание процессов с помощью процесса. Необходимо изменить уровни разрешений для этой учетной записи пользователя или обратиться к администратору учетной записи.

Эта ошибка также может возникать, если задан следующий раздел реестра:

\\\HKCU\Software\Microsoft\Windows\CurrentVersion\Policies\Explorer\RestrictRun

Чтобы устранить эту ошибку, удалите ключ Рестриктрун. Если требуется этот раздел реестра, добавьте **вкспавн. exe** в список записей ключа.

Еще одна причина этой ошибки заключается в том, что параметр политики не включает Вкспавн. exe в раздел реестра HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Policies\RestrictRun как разрешенное окно программы для этой учетной записи пользователя.

Дополнительные сведения см. в подразделе «Использование [параметров системной политики](/previous-versions/windows/desktop/Policy/adhering-to-system-policy-settings)» раздела «Запуск только разрешенных приложений Windows».