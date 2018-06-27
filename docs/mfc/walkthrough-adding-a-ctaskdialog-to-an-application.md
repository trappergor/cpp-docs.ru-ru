---
title: 'Пошаговое руководство: Добавление CTaskDialog в приложение | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTaskDialog, adding
- walkthroughs [MFC], dialogs
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e8e6c7d5f8144b2aec6c7783680feeff5f6f8a1
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951628"
---
# <a name="walkthrough-adding-a-ctaskdialog-to-an-application"></a>Пошаговое руководство. Добавление CTaskDialog в приложение
В этом пошаговом руководстве содержатся сведения о [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) и показано, как добавить его в приложение.  
  
 `CTaskDialog` Является диалоговым окном задачи, которое заменяет окно сообщения Windows в Windows Vista или более поздней версии. `CTaskDialog` улучшает исходное окно сообщения и расширяет его функциональные возможности. Окно сообщения Windows по-прежнему поддерживается в Visual Studio.  
  
> [!NOTE]
> Версиях Windows, более ранних, чем Windows Vista не поддерживают `CTaskDialog`. Чтобы сообщение отображалось для пользователей, запускающих приложение в более ранних версиях Windows, необходимо запрограммировать альтернативный вариант диалогового окна. Статический метод [CTaskDialog::IsSupported](../mfc/reference/ctaskdialog-class.md#issupported) во время выполнения позволит определить возможность отображения `CTaskDialog`. Кроме того, `CTaskDialog` доступно только в случае, если ваше приложение построено с помощью библиотеки юникода.  
  
 `CTaskDialog` поддерживает несколько необязательных элементов для сбора и отображения информации. Например, `CTaskDialog` может отображать ссылки на команды, настраиваемые кнопки, настраиваемые значки и нижний колонтитул. `CTaskDialog` также располагает рядом методов, которые позволяют запрашивать состояние диалогового окна задачи, чтобы определить, какие необязательные элементы выбрал пользователь.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
- Visual Studio 2010 или более поздней версии  
  
- Windows Vista или более поздней версии  
  
## <a name="replacing-a-windows-message-box-with-a-ctaskdialog"></a>Замена окна сообщения Windows на CTaskDialog  
 В следующей процедуре показан основной способ использования `CTaskDialog`, заменяющего окно сообщения Windows. В этом примере также демонстрируется изменение значка, связанного с диалоговым окном задачи. После изменения значка `CTaskDialog` отображается аналогично окну сообщения Windows.  
  
#### <a name="to-replace-a-windows-message-box-with-a-ctaskdialog"></a>Замена окна сообщения Windows на CTaskDialog  
  
1.  Создайте проект приложения MFC с параметрами по умолчанию. Она вызывается *MyProject*.  
  
2.  С помощью **обозревателя решений** открыть файл MyProject.cpp.  
  
3.  После списка включаемых файлов добавьте `#include "afxtaskdialog.h"` .  
  
4.  Найдите метод `CMyProjectApp::InitInstance`. Перед инструкцией `return TRUE;` вставьте приведенные далее строки кода. Этот код создает строки, используемые в окне сообщения Windows или в `CTaskDialog`.  
  
 ```  
    CString message("My message to the user");

    CString dialogTitle("My Task Dialog title");

    CString emptyString;  
 ```  
  
5.  После кода из шага 4 добавьте приведенный далее код. Этот код гарантирует, что на компьютере пользователя поддерживается `CTaskDialog`. Если диалоговое окно не поддерживается, в приложении отображается окно сообщения Windows.  
  
 ```  
    if (CTaskDialog::IsSupported())  
 {  
 
 }  
    else 
 {  
    AfxMessageBox(message);

 }  
 ```  
  
6.  Вставьте следующий код в квадратных скобках после **Если** инструкции на шаге 5. Этот код создает `CTaskDialog`.  
  
 ```  
    CTaskDialog taskDialog(message,
    emptyString,
    dialogTitle,
    TDCBF_OK_BUTTON);

 ```  
  
7.  На следующей строке добавьте следующий код. Этот код задает значок предупреждения.  
  
 ```  
    taskDialog.SetMainIcon(TD_WARNING_ICON);

 ```  
  
8.  На следующей строке добавьте следующий код. Этот код отображает диалоговое окно задачи.  
  
 ```  
    taskDialog.DoModal();

 ```  
  
 Если не требуется, чтобы для `CTaskDialog` отображался тот же значок, что и для окна сообщения Windows, можно пропустить шаг 7. Если этот шаг будет пропущен, при отображении у `CTaskDialog` не будет значка.  
  
 Скомпилируйте и запустите приложение. После запуска в приложении откроется диалоговое окно задачи.  
  
## <a name="adding-functionality-to-the-ctaskdialog"></a>Добавление функциональных возможностей в CTaskDialog  
 Ниже показано, как добавить функциональные возможности в окно `CTaskDialog` , созданное в предыдущей процедуре. В примере кода демонстрируется выполнение конкретных инструкций на основе выбора пользователя.  
  
#### <a name="to-add-functionality-to-the-ctaskdialog"></a>Добавление функциональных возможностей в CTaskDialog  
  
1.  Перейдите в **представление ресурсов**. Если **представление ресурсов**не отображается, его можно открыть из меню **Вид** .  
  
2.  Разверните **представление ресурсов** , чтобы увидеть папку **Таблица строк** . Разверните папку и дважды щелкните запись **Таблица строк** .  
  
3.  Перейдите в нижнюю часть таблицы строк и добавьте новую запись. Измените идентификатор на *TEMP_LINE1*. Задайте в качестве заголовка *Командная строка 1*.  
  
4.  Добавьте еще одну новую запись. Измените идентификатор на *TEMP_LINE2*. Задайте в качестве заголовка *Командная строка 2*.  
  
5.  Вернитесь к файлу MyProject.cpp.  
  
6.  После `CString emptyString;`добавьте следующий код:  
  
 ```  
    CString expandedLabel("Hide extra information");

    CString collapsedLabel("Show extra information");

    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");

 ```  
  
7.  Найдите инструкцию `taskDialog.DoModal()` и замените ее следующим кодом: Этот код обновит диалоговое окно задачи и добавит новые элементы управления.  
  
 ```  
    taskDialog.SetMainInstruction(L"Warning");

 taskDialog.SetCommonButtons(TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);

    taskDialog.LoadCommandControls(TEMP_LINE1,
    TEMP_LINE2);

    taskDialog.SetExpansionArea(expansionInfo,
    collapsedLabel,
    expandedLabel);

    taskDialog.SetFooterText(L"This is the a small footnote to the user");

    taskDialog.SetVerificationCheckboxText(L"Remember your selection");

 ```  
  
8.  Добавьте следующую строку кода для отображения диалогового окна задачи и получения сделанного пользователем выбора:  
  
 ```  
    INT_PTR result = taskDialog.DoModal();

 ```  
  
9. После вызова `taskDialog.DoModal()`вставьте следующий код: Этот раздел кода обрабатывает входные данные пользователя:  
  
 ```  
    if (taskDialog.GetVerificationCheckboxState())  
 { *// PROCESS IF the user selects the verification checkbox   
 }  
 
    switch (result)  
 {  
    case TEMP_LINE1: *// PROCESS IF the first command line  
    break; 
    case TEMP_LINE2: *// PROCESS IF the second command line  
    break; 
    case IDYES: *// PROCESS IF the user clicks yes  
    break; 
    case IDNO: *// PROCESS IF the user clicks no  
    break; 
    case IDCANCEL: *// PROCESS IF the user clicks cancel  
    break; 
    default: *// This case should not be hit because closing the dialog box results in IDCANCEL  
    break; 
 }  
 ```  
  
 В коде на шаге 9 замените комментарии, начинающиеся PROCESS IF, на код, который должен выполняться при определенных условиях.  
  
 Скомпилируйте и запустите приложение. В приложении откроется диалоговое окно задачи с новыми элементами управления и дополнительными сведениями.  
  
## <a name="displaying-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>Отображение CTaskDialog без создания объекта CTaskDialog  
 Ниже показано, как отобразить `CTaskDialog` без предварительного создания объекта `CTaskDialog` . Этот пример является продолжением предыдущей процедуры.  
  
#### <a name="to-display-a-ctaskdialog-without-creating-a-ctaskdialog-object"></a>Отображение CTaskDialog без создания объекта CTaskDialog  
  
1.  Откройте файл MyProject.cpp, если это еще не сделано.  
  
2.  Перейдите к закрывающей скобке инструкции `if (CTaskDialog::IsSupported())` .  
  
3.  Вставьте следующий код непосредственно перед закрывающей скобкой **Если** инструкции (перед **else** блок):  
  
 ```  
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message",
    L"Error",
    L"New Title",
    TEMP_LINE1,
    TEMP_LINE2);

 ```  
  
 Скомпилируйте и запустите приложение. В приложении откроются два диалоговых окна задач. Первое диалоговое окно — это окно из процедуры добавления функциональных возможностей в CTaskDialog. Второе окно — это окно из последней процедуры.  
  
 В этих примерах показаны не все доступные варианты для `CTaskDialog`, но они помогут вам приступить к работе. Полное описание класса см. в разделе [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) .  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Класс CTaskDialog](../mfc/reference/ctaskdialog-class.md)   
 [CTaskDialog::CTaskDialog](../mfc/reference/ctaskdialog-class.md#ctaskdialog)

