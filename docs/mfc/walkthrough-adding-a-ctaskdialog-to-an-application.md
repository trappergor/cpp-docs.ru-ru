---
title: "Пошаговое руководство. Добавление CTaskDialog в приложение | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTaskDialog, добавление"
  - "пошаговые руководства [C++], диалоговые окна"
ms.assetid: 3a62abb8-2d86-4bec-bdb8-5784d5f9a9f8
caps.latest.revision: 6
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Пошаговое руководство. Добавление CTaskDialog в приложение
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом пошаговом руководстве содержатся сведения о [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md) и показано, как добавить его в приложение.  
  
 `CTaskDialog` является диалоговым окном задачи, которое заменяет диалоговое окно сообщения Windows в [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)].`CTaskDialog` улучшает исходное окно сообщения и расширяет его функциональные возможности. Окно сообщения Windows по\-прежнему поддерживается в [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
> [!NOTE]
>  `CTaskDialog` не поддерживается в версиях Windows, более ранних, чем [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]. Чтобы сообщение отображалось для пользователей, запускающих приложение в более ранних версиях Windows, необходимо запрограммировать альтернативный вариант диалогового окна. Статический метод [CTaskDialog::IsSupported](../Topic/CTaskDialog::IsSupported.md) во время выполнения позволит определить возможность отображения `CTaskDialog` на компьютере пользователя. Кроме того, `CTaskDialog` доступно только в случае, если ваше приложение построено с помощью библиотеки юникода.  
  
 `CTaskDialog` поддерживает несколько необязательных элементов для сбора и отображения информации. Например, `CTaskDialog` может отображать ссылки на команды, настраиваемые кнопки, настраиваемые значки и нижний колонтитул.`CTaskDialog` также располагает рядом методов, которые позволяют запрашивать состояние диалогового окна задачи, чтобы определить, какие необязательные элементы выбрал пользователь.  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)]  
  
-   [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
## Замена окна сообщения Windows на CTaskDialog  
 В следующей процедуре показан основной способ использования `CTaskDialog`, заменяющего окно сообщения Windows. В этом примере также демонстрируется изменение значка, связанного с диалоговым окном задачи. После изменения значка `CTaskDialog` отображается аналогично окну сообщения Windows.  
  
#### Замена окна сообщения Windows на CTaskDialog  
  
1.  Создайте проект приложения MFC с параметрами по умолчанию. Назовите его `MyProject`.  
  
2.  С помощью **обозревателя решений** открыть файл MyProject.cpp.  
  
3.  После списка включаемых файлов добавьте `#include "afxtaskdialog.h"`.  
  
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
  
6.  После инструкции `if` из шага 5 вставьте в квадратных скобках приведенный далее код. Этот код создает `CTaskDialog`.  
  
    ```  
    CTaskDialog taskDialog(message, emptyString, dialogTitle, TDCBF_OK_BUTTON);  
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
  
## Добавление функциональных возможностей в CTaskDialog  
 Ниже показано, как добавить функциональные возможности в окно `CTaskDialog`, созданное в предыдущей процедуре. В примере кода демонстрируется выполнение конкретных инструкций на основе выбора пользователя.  
  
#### Добавление функциональных возможностей в CTaskDialog  
  
1.  Перейдите в **представление ресурсов**. Если **представление ресурсов** не отображается, его можно открыть из меню **Вид**.  
  
2.  Разверните **представление ресурсов**, чтобы увидеть папку **Таблица строк**. Разверните папку и дважды щелкните запись **Таблица строк**.  
  
3.  Перейдите в нижнюю часть таблицы строк и добавьте новую запись. Измените идентификатор на `TEMP_LINE1`. Задайте в качестве заголовка **Командная строка 1**.  
  
4.  Добавьте еще одну новую запись. Измените идентификатор на `TEMP_LINE2`. Задайте в качестве заголовка **Командная строка 2**.  
  
5.  Вернитесь к файлу MyProject.cpp.  
  
6.  После `CString emptyString;` добавьте следующий код:  
  
    ```  
    CString expandedLabel("Hide extra information");  
    CString collapsedLabel("Show extra information");  
    CString expansionInfo("This is the additional information to the user,\nextended over two lines.");  
    ```  
  
7.  Найдите инструкцию `taskDialog.DoModal()` и замените ее следующим кодом: Этот код обновит диалоговое окно задачи и добавит новые элементы управления.  
  
    ```  
    taskDialog.SetMainInstruction(L"Warning");  
    taskDialog.SetCommonButtons(TDCBF_YES_BUTTON | TDCBF_NO_BUTTON | TDCBF_CANCEL_BUTTON);  
    taskDialog.LoadCommandControls(TEMP_LINE1, TEMP_LINE2);  
    taskDialog.SetExpansionArea(expansionInfo, collapsedLabel, expandedLabel);  
    taskDialog.SetFooterText(L"This is the a small footnote to the user");  
    taskDialog.SetVerificationCheckboxText(L"Remember your selection");  
    ```  
  
8.  Добавьте следующую строку кода для отображения диалогового окна задачи и получения сделанного пользователем выбора:  
  
    ```  
    INT_PTR result = taskDialog.DoModal();  
    ```  
  
9. После вызова `taskDialog.DoModal()` вставьте следующий код: Этот раздел кода обрабатывает входные данные пользователя:  
  
    ```  
    if (taskDialog.GetVerificationCheckboxState() )  
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
          // This case should not be hit because closing the dialog box results in IDCANCEL  
          break;  
    }  
    ```  
  
 В коде на шаге 9 замените комментарии, начинающиеся PROCESS IF, на код, который должен выполняться при определенных условиях.  
  
 Скомпилируйте и запустите приложение. В приложении откроется диалоговое окно задачи с новыми элементами управления и дополнительными сведениями.  
  
## Отображение CTaskDialog без создания объекта CTaskDialog  
 Ниже показано, как отобразить `CTaskDialog` без предварительного создания объекта `CTaskDialog`. Этот пример является продолжением предыдущей процедуры.  
  
#### Отображение CTaskDialog без создания объекта CTaskDialog  
  
1.  Откройте файл MyProject.cpp, если это еще не сделано.  
  
2.  Перейдите к закрывающей скобке инструкции `if (CTaskDialog::IsSupported())`.  
  
3.  Пред закрывающей скобкой инструкции `if` \(перед блоком `else`\) вставьте следующий код:  
  
    ```  
    HRESULT result2 = CTaskDialog::ShowDialog(L"My error message", L"Error", L"New Title", TEMP_LINE1, TEMP_LINE2);  
    ```  
  
 Скомпилируйте и запустите приложение. В приложении откроются два диалоговых окна задач. Первое диалоговое окно — это окно из процедуры добавления функциональных возможностей в CTaskDialog. Второе окно — это окно из последней процедуры.  
  
 В этих примерах показаны не все доступные варианты для `CTaskDialog`, но они помогут вам приступить к работе. Полное описание класса см. в разделе [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md).  
  
## См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [CTaskDialog Class](../mfc/reference/ctaskdialog-class.md)   
 [CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md)