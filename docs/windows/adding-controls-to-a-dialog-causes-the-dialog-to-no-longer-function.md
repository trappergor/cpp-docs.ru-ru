---
title: "Добавление элементов управления в диалоговое окно приводит к прекращению работы диалогового окна | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], troubleshooting
- common controls, troubleshooting
- troubleshooting controls
- dialog boxes, troubleshooting
- dialog box controls, troubleshooting
- InitCommonControls
ms.assetid: b2dd4574-ea59-4343-8d65-b387cead5da6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0ec4825419c7a9d3c9bc35151b84c327a03325b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-controls-to-a-dialog-causes-the-dialog-to-no-longer-function"></a>Добавление элементов управления в диалоговое окно приводит к неработоспособности этого диалогового окна
После добавления стандартного элемента управления или управления форматированным редактированием в диалоговое окно, не появятся при тестировании диалоговое окно или само диалоговое окно не будет отображаться.  
  
 **Пример проблемы**  
  
1.  Создайте проект Win32, измените параметры приложения, поэтому создание приложения Windows (а не консольное приложение).  
  
2.  В [представление ресурсов](../windows/resource-view-window.md), дважды щелкните RC-файл.  
  
3.  В группе параметров диалогового окна щелкните **о** поле.  
  
4.  Добавить **контроль IP-адресов** в диалоговое окно.  
  
5.  Сохранить и **перестроить все**.  
  
6.  Запустите программу.  
  
7.  В диалоговом **справки** меню, нажмите кнопку **о** командной; ни одно диалоговое окно отображается поле.  
  
 **Причины**  
  
 В настоящий момент редактор диалоговых окон не добавляет автоматически код в проект при перетаскивании следующие стандартные элементы управления или элементы управления в диалоговое окно rich edit. И не Visual Studio обеспечивает ошибку или предупреждение при возникновении этой проблемы. Необходимо вручную добавить код для элемента управления.  
  
||||  
|-|-|-|  
|Элемент управления «Ползунок»|Управления "дерево"|Элемент управления "Выбор даты и времени"|  
|Элемент управления "Счетчик"|Элемент управления вкладки|Месячный календарь|  
|Элемент управления хода выполнения|Управления "анимация"|Контроль IP-адресов|  
|Сочетания клавиш|Элемент управления Rich Edit|Поле Расширенное поле со списком|  
|Список элементов управления|Элемент управления Rich Edit 2.0|Пользовательский элемент управления|  
  
## <a name="the-fix-for-common-controls"></a>Исправление для общих элементов управления  
 Для использования стандартных элементов управления в диалоговом окне, необходимо вызвать [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) или **AFXInitCommonControls** перед созданием диалоговым окном.  
  
## <a name="the-fix-for-richedit-controls"></a>Исправление для элементов управления RichEdit  
 Необходимо вызвать **LoadLibrary** для элемента управления rich edit. Дополнительные сведения см. в разделе [использование элемента управления RichEdit 1.0 с MFC](../windows/using-the-richedit-1-0-control-with-mfc.md), [о элементами управления Rich Edit](http://msdn.microsoft.com/library/windows/desktop/bb787873) в [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)], и [Общие сведения об элементе управления Rich Edit](../mfc/overview-of-the-rich-edit-control.md).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Устранение неполадок редактора диалоговых окон](../windows/troubleshooting-the-dialog-editor.md)   
 [Редактор диалоговых окон](../windows/dialog-editor.md)

