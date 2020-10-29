---
title: Сведения о добавлении поддержки ATL мастером ATL
ms.date: 08/20/2019
f1_keywords:
- vc.codewiz.atl.support
helpviewer_keywords:
- MFC, ATL support
- ATL, MFC projects
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
ms.openlocfilehash: aeac01ce58deb429f14058c06524dff53abde060
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924446"
---
# <a name="details-of-atl-support-added-by-the-atl-wizard"></a>Сведения о добавлении поддержки ATL мастером ATL

::: moniker range=">=msvc-160"

При [добавлении поддержки ATL к существующему исполняемому файлу MFC или библиотеке DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)Visual Studio добавляет файл заголовка *Framework. h* по умолчанию, который содержит `#include` `#define` директивы препроцессора, и позволяет использовать ATL в проекте. Дополнительные файлы или классы не добавляются, как было сделано в предыдущих версиях Visual Studio.

::: moniker-end

::: moniker range="<=msvc-150"

При [добавлении поддержки ATL в существующий исполняемый файл MFC или библиотеку DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)Visual Studio вносит следующие изменения в существующий проект MFC (в этом примере вызывается проект `MFCEXE` ):

- Добавляются два новых файла (IDL-файл и файл. rgs, используемый для регистрации сервера).

- В основном файле заголовка приложения и файлов реализации (Мфцексе. h и Мфцексе. cpp) добавляется новый класс (производный от `CAtlMFCModule` ). В дополнение к новому классу код добавляется в `InitInstance` для регистрации. Код также добавляется в `ExitInstance` функцию для отмены объекта класса. В файле заголовка, наконец, в файл реализации включены два новых файла заголовков (Инитгуид. h и Mfcexe_i. c), объявляя и инициализируя новые идентификаторы GUID для `CAtlMFCModule` класса, производного от.

- Для правильной регистрации сервера в файл ресурсов проекта добавляется запись для нового RGS-файла.

::: moniker-end

## <a name="notes-for-dll-projects"></a>Примечания для проектов DLL

При добавлении поддержки ATL в проект MFC DLL вы увидите некоторые различия. Код добавляется в `DLLRegisterServer` функции и `DLLUnregisterServer` для регистрации и отмены регистрации библиотеки DLL. Код также добавляется в [DllCanUnloadNow](../../atl/reference/catldllmodulet-class.md#dllcanunloadnow) и [DllGetClassObject](../../atl/reference/catldllmodulet-class.md#dllgetclassobject).

## <a name="see-also"></a>См. также статью

[Поддержка ATL в проекте MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)<br/>
[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Добавление класса](../../ide/adding-a-class-visual-cpp.md)<br/>
[Добавление функции-члена](../../ide/adding-a-member-function-visual-cpp.md)<br/>
[Добавление переменной-члена](../../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Переопределение виртуальной функции](../../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[Обработчик сообщений MFC](../../mfc/reference/adding-an-mfc-message-handler.md)<br/>
[Перемещение по структуре класса](../../ide/navigate-code-cpp.md)
