---
title: Изменение шрифта текста на изображении (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5a86748d5a51e433e2e90450593ef1bac1c8de3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596285"
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>Изменение шрифта текста на изображении (редактор изображений для значков)

Следующая процедура является примером того, как:

- Добавление текста в значок в приложении Windows

- Управление шрифтом текста

### <a name="to-change-the-font-of-text-on-an-image"></a>Изменение шрифта текста на изображении

1. Создание приложения C++ Windows Forms. Дополнительные сведения см. в разделе [Создание проекта приложения Windows](http://msdn.microsoft.com/b2f93fed-c635-4705-8d0e-cf079a264efa). [Шаблон приложения Windows Forms](http://msdn.microsoft.com/1babdebf-ab3f-4a64-a608-98499a5b9cea) добавляет в файл с именем `app.ico` в проект по умолчанию.

2. В **обозревателе решений**, дважды щелкните файл app.ico. [Редактор изображений](../windows/image-editor-for-icons.md) будет открыт.

3. Из **изображение** меню, выберите **средства** , а затем выберите **текст**. [Диалогового текст](../windows/text-tool-dialog-box-image-editor-for-icons.md) будет отображаться.

4. В **текст** диалоговом окне `C++` в пустой текстовой области. Этот текст будет отображаться в поле с изменяемыми размерами в верхнем левом углу `app.ico`в **редактор изображений**.

5. В **редактор изображений**, перетащите поле с изменяемыми размерами центр app.ico, чтобы улучшить читаемость текста.

6. В **текст** диалоговом окне щелкните **шрифта** кнопки. [Шрифт текста-диалоговое окно](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) будет отображаться.

7. В **шрифт текста** выберите **Times New Roman** из списка доступных шрифтов, которые перечислены в **шрифта** поле со списком.

8. Выберите **Полужирный** из списка доступных стилей в **стиль шрифта** поле со списком.

9. Выберите **10** из списка доступных размеров в **размер** поле со списком.

10. Нажмите кнопку **ОК** кнопки. **Шрифт текста** диалоговое окно закроется, и новые параметры шрифта будет применяться к тексту.

11. Нажмите кнопку **закрыть** кнопку **текст** диалоговое окно. Можно изменять поля вокруг текста удаляются из **редактор изображений**.

## <a name="see-also"></a>См. также

[Изменение графических ресурсов](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[ToolBar](../windows/toolbar-image-editor-for-icons.md)