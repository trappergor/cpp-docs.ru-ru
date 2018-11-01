---
title: Сведения о добавлении поддержки ATL мастером ATL
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: 5684e1f53e9df120feca89cbb6b2ba70bd38d439
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564779"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Сведения о добавлении поддержки ATL мастером ATL

Когда вы [Добавление поддержки ATL в существующий исполняемый файл MFC или библиотеки DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C++ выполняет следующие изменения в существующий проект MFC (в этом примере проект называется `MFCEXE`):

- Добавляются два новых файла (IDL-файл и RGS-файл, используемый для регистрации сервера).

- В файлы основного приложения заголовка и реализации (Mfcexe.h и Mfcexe.cpp) новый класс (производный от `CAtlMFCModule`) добавляется. Помимо нового класса добавляется код `InitInstance` для регистрации. Код также добавляется `ExitInstance` функции для объекта класса. В файле заголовка, и, наконец, два новых файла заголовка (Initguid.h и Mfcexe_i.c) включены в файл реализации, в объявлении и инициализации новые идентификаторы GUID для `CAtlMFCModule`-производного класса.

- Чтобы зарегистрировать сервер должным образом, файл ресурсов проекта добавляется запись для нового RGS-файла.

## <a name="notes-for-dll-projects"></a>Примечания для проектов DLL

При добавлении поддержки ATL в проект библиотеки DLL MFC, вы увидите некоторые различия. Код добавляется `DLLRegisterServer` и `DLLUnregisterServer` функции для регистрации и отмены регистрации библиотеки DLL. Код также добавляется [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) и [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).

## <a name="see-also"></a>См. также

[Поддержка ATL в проект MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Перемещение по структуре класса](../../ide/navigating-the-class-structure-visual-cpp.md)
