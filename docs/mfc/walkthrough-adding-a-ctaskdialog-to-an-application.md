---
title: Пошаговое руководство. Добавление CTaskDialog в приложение
ms.date: 04/25/2019
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
ms.openlocfilehash: 3a970df4911fed643045a1c6b59fcda1a853dbcf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222775"
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>Пошаговое руководство. Добавление CTaskDialog в приложение

В этом пошаговом руководстве содержатся сведения о [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) и показано, как добавить его в приложение.

`CTaskDialog`Диалоговое окно является задачей, которое заменяет окно сообщения Windows в Windows Vista или более поздней версии. `CTaskDialog` улучшает исходное окно сообщения и расширяет его функциональные возможности. Окно сообщения Windows по-прежнему поддерживается в Visual Studio.

> [!NOTE]
> Версии Windows, предшествующие Windows Vista, не поддерживают `CTaskDialog` . Чтобы сообщение отображалось для пользователей, запускающих приложение в более ранних версиях Windows, необходимо запрограммировать альтернативный вариант диалогового окна. Статический метод [CTaskDialog::IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) во время выполнения позволит определить возможность отображения `CTaskDialog`. Кроме того, `CTaskDialog` доступно только в случае, если ваше приложение построено с помощью библиотеки юникода.

`CTaskDialog` поддерживает несколько необязательных элементов для сбора и отображения информации. Например, `CTaskDialog` может отображать ссылки на команды, настраиваемые кнопки, настраиваемые значки и нижний колонтитул. `CTaskDialog` также располагает рядом методов, которые позволяют запрашивать состояние диалогового окна задачи, чтобы определить, какие необязательные элементы выбрал пользователь.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения этого пошагового руководства требуются следующие компоненты:

- Visual Studio 2010 или более поздней версии

- Windows Vista или более поздней версии

## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Замена окна сообщения Windows на CTaskDialog

В следующей процедуре показан основной способ использования `CTaskDialog`, заменяющего окно сообщения Windows. В этом примере также демонстрируется изменение значка, связанного с диалоговым окном задачи. При изменении значка отображается то же значение, что и в `CTaskDialog` окне сообщения Windows.

### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>Замена окна сообщения Windows на CTaskDialog

1. Используйте **Мастер приложений MFC** для создания приложения MFC со всеми параметрами по умолчанию. Инструкции по открытию мастера для вашей версии Visual Studio см. в разделе [Пошаговое руководство. Использование новых элементов управления оболочки MFC](walkthrough-using-the-new-mfc-shell-controls.md) .

1. Назовите *MyProject*.

1. С помощью **обозревателя решений** открыть файл MyProject.cpp.

1. После списка включаемых файлов добавьте `#include "afxtaskdialog.h"` .

1. Найдите метод `CMyProjectApp::InitInstance`. Перед инструкцией `return TRUE;` вставьте приведенные далее строки кода. Этот код создает строки, используемые в окне сообщения Windows или в `CTaskDialog`.

    ```cpp
    CString message("My message to the user");
    CString dialogTitle("My Task Dialog title");
    CString emptyString;
    ```

1. После кода из шага 4 добавьте приведенный далее код. Этот код гарантирует, что на компьютере пользователя поддерживается `CTaskDialog`. Если диалоговое окно не поддерживается, приложение отображает окно сообщения Windows.

    ```cpp
    if (CTaskDialog::IsSupported())
    {

    }
    else
    {
        AfxMessageBox(message);
    }
    ```

1. Вставьте следующий код между скобками после **`if`** оператора из шага 5. Этот код создает `CTaskDialog`.

    ```cpp
    CTaskDialog taskDialog(message, emptyString, dialogTitle, TDCBF_OK_BUTTON);
    ```

1. На следующей строке добавьте следующий код. Этот код задает значок предупреждения.

    ```cpp
    taskDialog.SetMainIcon(TD_WARNING_ICON);
    ```

1. На следующей строке добавьте следующий код. Этот код отображает диалоговое окно задачи.

    ```cpp
    taskDialog.DoModal();
    ```

Если вы не хотите, `CTaskDialog` чтобы элемент отображал тот же значок, что и окно сообщения Windows, можно избежать шага 7. Если это не так, то `CTaskDialog` значок не имеет значка, когда приложение отображает его.

Скомпилируйте и запустите приложение. После запуска в приложении откроется диалоговое окно задачи.

## <a name="adding-functionality-to-the-ctaskdialog"></a>Добавление функциональных возможностей в CTaskDialog

Ниже показано, как добавить функциональные возможности в окно `CTaskDialog` , созданное в предыдущей процедуре. В примере кода демонстрируется выполнение конкретных инструкций на основе выбора пользователя.

### <a name="to-add-functionality-to-the-ctaskdialog"></a>Добавление функциональных возможностей в CTaskDialog

1. Перейдите в **представление ресурсов**. Если **представление ресурсов**не отображается, его можно открыть в меню **вид** .

1. Разверните **представление ресурсов** , чтобы увидеть папку **Таблица строк** . Разверните папку и дважды щелкните запись **Таблица строк** .

1. Перейдите в нижнюю часть таблицы строк и добавьте новую запись. Измените идентификатор на `TEMP_LINE1`. Задайте в качестве заголовка **Командная строка 1**.

1. Добавьте еще одну новую запись. Измените идентификатор на `TEMP_LINE2`. Задайте в качестве заголовка **Командная строка 2**.

1. Вернитесь к файлу MyProject.cpp.

1. После `CString emptyString;`добавьте следующий код:

    ```cpp
    CString expandedLabel("Hide extra information");
    CString collapsedLabel("Show extra information");
    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");
    ```

1. Найдите инструкцию `taskDialog.DoModal()` и замените ее следующим кодом: Этот код обновит диалоговое окно задачи и добавит новые элементы управления.

    ```cpp
    taskDialog.SetMainInstruction(L"Warning");
    taskDialog.SetCommonButtons(
        TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);
    taskDialog.LoadCommandControls(TEMP_LINE1, TEMP_LINE2);
    taskDialog.SetExpansionArea(
        expansionInfo, collapsedLabel, expandedLabel);
    taskDialog.SetFooterText(L"This is the a small footnote to the user");
    taskDialog.SetVerificationCheckboxText(L"Remember your selection");
    ```

1. Добавьте следующую строку кода для отображения диалогового окна задачи и получения сделанного пользователем выбора:

    ```cpp
    INT_PTR result = taskDialog.DoModal();
    ```

1. После вызова `taskDialog.DoModal()`вставьте следующий код: Этот раздел кода обрабатывает входные данные пользователя:

    ```cpp
    if (taskDialog.GetVerificationCheckboxState())
    {
        // PROCESS IF the user selects the verification checkbox
    }

    switch (result)
    {
    case TEMP_LINE1:
        // PROCESS IF the first command line
        break;
    case TEMP_LINE2:
        // PROCESS IF the second command line
        break;
    case IDYES:
        // PROCESS IF the user clicks yes
        break;
    case IDNO:
        // PROCESS IF the user clicks no
        break;
    case IDCANCEL:
        // PROCESS IF the user clicks cancel
        break;
    default:
        // This case should not be hit because closing
        // the dialog box results in IDCANCEL
        break;
    }
    ```

В коде на шаге 9 замените комментарии, начинающиеся с, `PROCESS IF` кодом, который требуется выполнить при указанных условиях.

Скомпилируйте и запустите приложение. В приложении откроется диалоговое окно задачи с новыми элементами управления и дополнительными сведениями.

## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>Отображение CTaskDialog без создания объекта CTaskDialog

Ниже показано, как отобразить `CTaskDialog` без предварительного создания объекта `CTaskDialog` . Этот пример является продолжением предыдущей процедуры.

### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>Отображение CTaskDialog без создания объекта CTaskDialog

1. Откройте файл MyProject. cpp, если он еще не открыт.

1. Перейдите к закрывающей скобке инструкции `if (CTaskDialog::IsSupported())` .

1. Вставьте следующий код непосредственно перед закрывающей скобкой **`if`** оператора (перед **`else`** блоком):

    ```cpp
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
        L"Error",
        L"New Title",
        TEMP_LINE1,
        TEMP_LINE2);
    ```

Скомпилируйте и запустите приложение. В приложении откроются два диалоговых окна задач. Первое диалоговое окно — из, **чтобы добавить функциональные возможности** в процедуру CTaskDialog. Второе диалоговое окно — из последней процедуры.

В этих примерах не показаны все доступные параметры для `CTaskDialog` , но они помогут вам приступить к работе. Полное описание класса см. в разделе [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) .

## <a name="see-also"></a>См. также раздел

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Класс CTaskDialog](../mfc/reference/ctaskdialog-class.md)<br/>
[CTaskDialog:: CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)
