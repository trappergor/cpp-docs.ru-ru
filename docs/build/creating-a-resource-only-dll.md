---
title: Создание библиотеки ресурсов DLL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource-only DLLs [C++], creating
- DLLs [C++], creating
ms.assetid: e6b1d4da-7275-467f-a58c-a0a8a5835199
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea6590a57a336740be0a9439c959ebe32239d4e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703466"
---
# <a name="creating-a-resource-only-dll"></a>Создание библиотек DLL, содержащих только ресурсы

Библиотеки DLL ресурсов представляет собой библиотеку DLL, в которой содержатся только ресурсы, такие как значки, растровые изображения, строки и диалоговые окна. Использование библиотеки DLL ресурсов — хороший способ совместно использовать тот же набор ресурсов несколькими программами. Также рекомендуется использовать приложение с ресурсы, локализованные для нескольких языков (см. в разделе [локализованные ресурсы в приложениях MFC: вспомогательные библиотеки DLL](../build/localized-resources-in-mfc-applications-satellite-dlls.md)).

Чтобы создать Библиотеку ресурсов, создайте новый проект библиотеки DLL Win32 (не MFC) и добавьте ресурсы в проект.

- Выберите проект Win32 в **новый проект** диалоговое окно и укажите тип проекта библиотеки DLL в мастере проектов Win32.

- Создайте новый скрипт ресурсов, содержащий ресурсы (например, строка или меню) для библиотеки DLL и сохраните RC-файл.

- На **проекта** меню, щелкните **добавить существующий элемент**и вставьте в проект новый RC-файл.

- Укажите [/NOENTRY](../build/reference/noentry-no-entry-point.md) параметр компоновщика. / NOENTRY запрещает компоновщику добавлял ссылку на `_main` в библиотеку DLL; это необходимо для создания библиотеки DLL только ресурсы.

- Построение библиотеки DLL.

Приложение, которое использует библиотеку DLL ресурсов следует вызывать [LoadLibrary](../build/loadlibrary-and-afxloadlibrary.md) явной ссылкой на библиотеку DLL. Доступ к ресурсам, вызовите универсальные функции `FindResource` и `LoadResource`, которой работают для любых ресурсов, или вызовите один из следующих функций конкретного ресурса:

- `FormatMessage`

- `LoadAccelerators`

- `LoadBitmap`

- `LoadCursor`

- `LoadIcon`

- `LoadMenu`

- `LoadString`

Приложение должно вызвать `FreeLibrary` после завершения использования ресурсов.

## <a name="see-also"></a>См. также

[Работа с файлами ресурсов](../windows/working-with-resource-files.md)<br/>
[DLL в Visual C++](../build/dlls-in-visual-cpp.md)