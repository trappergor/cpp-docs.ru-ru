---
title: Создание всплывающей подсказки для кнопки панели инструментов (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor [C++], creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2d03b71f862e31a2bef25d89c0347c95da240642
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422679"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button-c"></a>Создание всплывающей подсказки для кнопки панели инструментов (C++)

### <a name="to-create-a-tool-tip"></a>Создание всплывающей подсказки

1. Нажмите кнопку панели инструментов.

2. В [окно "Свойства"](/visualstudio/ide/reference/properties-window)в **Prompt** поле свойства, добавьте описание кнопки для строки состояния; после сообщения, добавьте `\n` и имя всплывающей подсказки.

Распространенным примером во всплывающей подсказке является **печати** кнопку **WordPad**:

1. Откройте **WordPad**.

2. Наведите указатель мыши **печати** кнопки на панели инструментов.

3. Обратите внимание, что слово `Print` теперь располагается под указателем мыши.

4. Посмотрите на строке состояния (в самом низу окна **WordPad** окна)-Обратите внимание на то, что теперь отображается текст `Prints the active document`.

`Print` В **шаг 3** — «имя совет средство» и `Prints the active document` из **шаг 4** — «описание кнопки для строки состояния.»

Если этот эффект с помощью функции **инструментов** редактора, можно задать **Prompt** свойства `Prints the active document\nPrint`.

> [!NOTE]
> Можно изменить с помощью текст приглашения [окно "Свойства"](/visualstudio/ide/reference/properties-window).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

MFC или ATL

## <a name="see-also"></a>См. также

[Создание, перемещение и редактирование кнопок на панели инструментов](../windows/creating-moving-and-editing-toolbar-buttons.md)<br/>
[Редактор панелей инструментов](../windows/toolbar-editor.md)