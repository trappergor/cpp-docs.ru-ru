---
title: "CTaskDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTaskDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTaskDialog class"
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CTaskDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Всплывающее диалоговое окно, которое действует как окно сообщения, но может выводить дополнительную информацию для пользователя.  `CTaskDialog` также включает функции для сбора сведений от пользователя.  
  
## Синтаксис  
  
```  
class CTaskDialog : public CObject  
```  
  
## Члены  
  
### Конструкторы  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md)|Создает объект `CTaskDialog`.|  
  
### Методы  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](../Topic/CTaskDialog::AddCommandControl.md)|Добавляет элемент управления кнопки `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](../Topic/CTaskDialog::AddRadioButton.md)|Добавить переключатель в `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](../Topic/CTaskDialog::ClickCommandControl.md)|Выберите управление кнопки или распространенной кнопку программными средствами.|  
|[CTaskDialog::ClickRadioButton](../Topic/CTaskDialog::ClickRadioButton.md)|Щелкните переключатель программно.|  
|[CTaskDialog::DoModal](../Topic/CTaskDialog::DoModal.md)|Выводит `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonCount](../Topic/CTaskDialog::GetCommonButtonCount.md)|Извлекает число доступных общих кнопок.|  
|[CTaskDialog::GetCommonButtonFlag](../Topic/CTaskDialog::GetCommonButtonFlag.md)|Преобразование стандартной кнопки Windows к общему типу кнопки, связанный с классом `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonId](../Topic/CTaskDialog::GetCommonButtonId.md)|Новообращенные одно общих типов кнопки, связанных с классом `CTaskDialog` к стандартной кнопки Windows.|  
|[CTaskDialog::GetOptions](../Topic/CTaskDialog::GetOptions.md)|Возвращает флаги параметров для данного `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](../Topic/CTaskDialog::GetSelectedCommandControlID.md)|Возвращает выбранный элемент управления кнопки.|  
|[CTaskDialog::GetSelectedRadioButtonID](../Topic/CTaskDialog::GetSelectedRadioButtonID.md)|Возвращает выбранный переключатель.|  
|[CTaskDialog::GetVerificationCheckboxState](../Topic/CTaskDialog::GetVerificationCheckboxState.md)|Извлекает состояние флажка проверки.|  
|[CTaskDialog::IsCommandControlEnabled](../Topic/CTaskDialog::IsCommandControlEnabled.md)|Указывает, включены ли элемент управления кнопки или распространенной.|  
|[CTaskDialog::IsRadioButtonEnabled](../Topic/CTaskDialog::IsRadioButtonEnabled.md)|Указывает, включен ли переключатель.|  
|[CTaskDialog::IsSupported](../Topic/CTaskDialog::IsSupported.md)|Определяет, поддерживает ли компьютер, на котором выполняется приложение `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](../Topic/CTaskDialog::LoadCommandControls.md)|Добавляет управления button с помощью данных из таблицы строки.|  
|[CTaskDialog::LoadRadioButtons](../Topic/CTaskDialog::LoadRadioButtons.md)|Добавляет переключатели с помощью данных из таблицы строки.|  
|[CTaskDialog::NavigateTo](../Topic/CTaskDialog::NavigateTo.md)|Передает фокус на другой `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](../Topic/CTaskDialog::OnCommandControlClick.md)|Платформа вызывает этот метод, когда пользователь щелкает элемент управления кнопки.|  
|[CTaskDialog::OnCreate](../Topic/CTaskDialog::OnCreate.md)|Платформа вызывает этот метод после того, как они создают `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](../Topic/CTaskDialog::OnDestroy.md)|Платформа вызывает этот метод непосредственно перед их разрушают `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](../Topic/CTaskDialog::OnExpandButtonClick.md)|Платформа вызывает этот метод, когда пользователь щелкает кнопку расширения.|  
|[CTaskDialog::OnHelp](../Topic/CTaskDialog::OnHelp.md)|Границы вызывают этот метод, если пользователь запросит справку.|  
|[CTaskDialog::OnHyperlinkClick](../Topic/CTaskDialog::OnHyperlinkClick.md)|Платформа вызывает этот метод, когда пользователь щелкает гиперссылку.|  
|[CTaskDialog::OnInit](../Topic/CTaskDialog::OnInit.md)|Платформа вызывает этот метод, когда `CTaskDialog` инициализируется.|  
|[CTaskDialog::OnNavigatePage](../Topic/CTaskDialog::OnNavigatePage.md)|Платформа вызывает этот метод, когда пользователь перемещает фокус в отношении элементов управления на `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](../Topic/CTaskDialog::OnRadioButtonClick.md)|Платформа вызывает этот метод, когда пользователь выбирает элемент управления переключателя.|  
|[CTaskDialog::OnTimer](../Topic/CTaskDialog::OnTimer.md)|Платформа вызывает этот метод, когда таймера истекает.|  
|[CTaskDialog::OnVerificationCheckboxClick](../Topic/CTaskDialog::OnVerificationCheckboxClick.md)|Платформа вызывает этот метод, когда пользователь щелкает флажок проверки.|  
|[CTaskDialog::RemoveAllCommandControls](../Topic/CTaskDialog::RemoveAllCommandControls.md)|Удаляет все командные управления из `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](../Topic/CTaskDialog::RemoveAllRadioButtons.md)|Удаляет все переключатели из `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](../Topic/CTaskDialog::SetCommandControlOptions.md)|Обновляет управление кнопками в `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](../Topic/CTaskDialog::SetCommonButtonOptions.md)|Обновляет подмножество общих кнопок для включения и требует высоты контроля учетных записей.|  
|[CTaskDialog::SetCommonButtons](../Topic/CTaskDialog::SetCommonButtons.md)|Добавить общие кнопки `CTaskDialog`.|  
|[CTaskDialog::SetContent](../Topic/CTaskDialog::SetContent.md)|Обновляет содержимое `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](../Topic/CTaskDialog::SetDefaultCommandControl.md)|Указывает значение по умолчанию элемент управления кнопки.|  
|[CTaskDialog::SetDefaultRadioButton](../Topic/CTaskDialog::SetDefaultRadioButton.md)|Указывает значение по умолчанию переключателя.|  
|[CTaskDialog::SetDialogWidth](../Topic/CTaskDialog::SetDialogWidth.md)|Корректирует ширину `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](../Topic/CTaskDialog::SetExpansionArea.md)|Обновляет область расширения `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](../Topic/CTaskDialog::SetFooterIcon.md)|Значок обновления нижнего колонтитула страницы, чтобы `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](../Topic/CTaskDialog::SetFooterText.md)|Обновляет текста в нижнем колонтитуле `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](../Topic/CTaskDialog::SetMainIcon.md)|Обновляет главный значок `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](../Topic/CTaskDialog::SetMainInstruction.md)|Обновляет главная инструкция `CTaskDialog`.|  
|[CTaskDialog::SetOptions](../Topic/CTaskDialog::SetOptions.md)|Настраивает параметры для `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](../Topic/CTaskDialog::SetProgressBarMarquee.md)|Настраивает панель бегущей строки для `CTaskDialog` и добавляет ее к компоненту.|  
|[CTaskDialog::SetProgressBarPosition](../Topic/CTaskDialog::SetProgressBarPosition.md)|Корректирует положение индикатора выполнения.|  
|[CTaskDialog::SetProgressBarRange](../Topic/CTaskDialog::SetProgressBarRange.md)|Настраивает диапазон индикатора выполнения.|  
|[CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md)|Устанавливает состояние индикатора выполнения и отображает его на `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](../Topic/CTaskDialog::SetRadioButtonOptions.md)|Включение или отключение переключатель.|  
|[CTaskDialog::SetVerificationCheckbox](../Topic/CTaskDialog::SetVerificationCheckbox.md)|Устанавливает состояние флажка флажок проверки.|  
|[CTaskDialog::SetVerificationCheckboxText](../Topic/CTaskDialog::SetVerificationCheckboxText.md)|Устанавливает текст в правой части флажка проверки.|  
|[CTaskDialog::SetWindowTitle](../Topic/CTaskDialog::SetWindowTitle.md)|Задает заголовок `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](../Topic/CTaskDialog::ShowDialog.md)|Создает и отображает `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](../Topic/CTaskDialog::TaskDialogCallback.md)|Платформа вызывает функцию в ответ на различные сообщения Windows.|  
  
### Элементы данных  
  
|||  
|-|-|  
|`m_aButtons`|Массив элементов управления кнопки для `CTaskDialog`.|  
|`m_aRadioButtons`|Массив элементов управления переключателя для `CTaskDialog`.|  
|`m_bVerified`|`TRUE` указывает, что флажок проверка проверки; `FALSE` указывает, что объект отсутствует.|  
|`m_footerIcon`|Значок в нижнем колонтитуле `CTaskDialog`.|  
|`m_hWnd`|Дескриптор окна для `CTaskDialog`.|  
|`m_mainIcon`|Главный значок `CTaskDialog`.|  
|`m_nButtonDisabled`|Маска, которая указывает, что из общих кнопок отключен.|  
|`m_nButtonElevation`|Маска, которая указывает, что из общих высоту кнопок требует контроля учетных записей.|  
|`m_nButtonId`|Идентификатор выбранного элемента управления button.|  
|`m_nCommonButton`|Маска, определяющая кнопки отображаются на `CTaskDialog`, общие.|  
|`m_nDefaultCommandControl`|Идентификатор элемента управления выделен кнопки, когда `CTaskDialog`.|  
|`m_nDefaultRadioButton`|Идентификатор элемента управления переключателя, выделен при `CTaskDialog`.|  
|`m_nFlags`|Маска, определяющая параметры для `CTaskDialog`.|  
|`m_nProgressPos`|Текущая позиция для индикатора выполнения.  Это значение должно принадлежать диапазону от `m_nProgressRangeMin` до `m_nProgressRangeMax`.|  
|`m_nProgressRangeMax`|Максимальное значение, допустимое для индикатора выполнения.|  
|`m_nProgressRangeMin`|Минимальное значение для индикатора выполнения.|  
|`m_nProgressState`|Состояние индикатора выполнения.  Дополнительные сведения см. в разделе [CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md).|  
|`m_nRadioId`|Идентификатор выбранного управления переключателя.|  
|`m_nWidth`|Ширина `CTaskDialog` \(в пикселях\).|  
|`m_strCollapse`|Строка `CTaskDialog` отображается справа от окна расширения при скрыто \- развернут сведения.|  
|`m_strContent`|Строка `CTaskDialog` содержимого.|  
|`m_strExpand`|Строка `CTaskDialog` отображается справа от окна расширения при \- развернут информации.|  
|`m_strFooter`|Нижний колонтитул `CTaskDialog`.|  
|`m_strInformation`|Сведения для `CTaskDialog`\- развернут.|  
|`m_strMainInstruction`|Основная инструкция `CTaskDialog`.|  
|`m_strTitle`|Заголовок `CTaskDialog`.|  
|`m_strVerification`|Эта строка выводится справа от `CTaskDialog` флажок проверки.|  
  
## Заметки  
 Класс `CTaskDialog` заменяет стандартное окно сообщения Windows и имеет дополнительные возможности, как новые элементы управления для сбора сведений от пользователя.  Этот класс в библиотеке MFC в [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  `CTaskDialog` доступен, начиная с [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  Более ранние версии Windows не могут отображать объект `CTaskDialog`.  Используйте `CTaskDialog::IsSupported` для указания во время выполнения, может ли текущий пользователь открыть диалоговое окно задачи.  Окно сообщения Windows стандарта по\-прежнему поддерживается в [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 `CTaskDialog` доступно только при построении приложения с помощью библиотеки юникод.  
  
 `CTaskDialog` имеется 2 разных конструктора.  Один конструктор позволяет указать 2 кнопки и максимум 6 обычных элементов управления "Кнопка".  Можно добавить несколько кнопок после создания `CTaskDialog`.  Второй конструктор не поддерживает никаких кнопки, но можно добавлять неограниченное число обычных элементов управления "Кнопка".  Дополнительные сведения о конструкторах см. в разделе [CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md).  
  
 Следующий образ показывает образец `CTaskDialog` для демонстрации расположение некоторых элементов управления.  
  
 ![Пример CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialogSample")  
Образец CTaskDialog  
  
## Требования  
 **Операционная система минимальное требуемое:** [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **заголовок:** afxtaskdialog.h  
  
## См. также  
 [Классы](../Topic/MFC%20Classes.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Пошаговое руководство. Добавление CTaskDialog в приложение](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)