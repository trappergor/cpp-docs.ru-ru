---
title: "Изменение шрифта текста на изображении (редактор изображений для значков) | Документы Microsoft"
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
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07dc7d7fd74ad9d4b0229ffef7cf4e96a4ea44b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>Изменение шрифта текста на изображении (редактор изображений для значков)
Ниже приведен пример того, как:  
  
-   Добавить текст к значку в приложении Windows  
  
-   Управление шрифтом текст  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>Изменение шрифта текста на изображении  
  
1.  Создание приложения C++ для Windows Forms. Дополнительные сведения см. в разделе [Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa). [Шаблон приложения Windows Forms](http://msdn.microsoft.com/en-us/1babdebf-ab3f-4a64-a608-98499a5b9cea) добавляет в файл с именем app.ico в проект по умолчанию.  
  
2.  В обозревателе решений дважды щелкните файл app.ico. [Редактора изображений](../windows/image-editor-for-icons.md) будет открыт.  
  
3.  Из **изображения** последовательно выберите пункты **средства** , а затем выберите **текст**. [Диалоговое окно текст](../windows/text-tool-dialog-box-image-editor-for-icons.md) будут отображаться.  
  
4.  В текстовом поле диалогового окна инструментов введите `C++` в области пустой текст. Этот текст будет отображаться в поле с изменяемыми размерами в верхнем левом углу app.ico в редакторе изображений.  
  
5.  В редакторе изображений перетащите поле с изменяемыми размерами в центр app.ico для повышения удобства чтения текста.  
  
6.  В текстовом поле диалогового окна инструментов, нажмите кнопку **шрифта** кнопки. ["Шрифт текста диалогового окна"](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) будет отображаться.  
  
7.  В диалоговое окно "Шрифт текста» выберите « **Times New Roman** из списка доступных шрифтов, которые перечислены в **шрифта** списка.  
  
8.  Выберите **Полужирный** из списка доступных стилей в **стиль шрифта** списка.  
  
9. Выберите **10** из списка доступных размеров в **размер** списка.  
  
10. Нажмите кнопку **ОК** кнопки. Диалоговое окно шрифтов текста будет закрыт, и новые параметры шрифта будут применены к тексту.  
  
11. Нажмите кнопку **закрыть** кнопку диалогового окна текст. Поле с изменяемыми размерами вокруг текста не будут появляться в редакторе изображений.  
  
## <a name="see-also"></a>См. также  
 [Редактирование графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Панель инструментов](../windows/toolbar-image-editor-for-icons.md)

