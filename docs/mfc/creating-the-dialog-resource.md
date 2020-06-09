---
title: Создание ресурса диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- dialog resources
- MFC dialog boxes [MFC], creating
- dialog templates [MFC], creating dialog resource
- templates [MFC], creating
- resources [MFC], creating dialog boxes
- MFC dialog boxes [MFC], dialog resource
ms.assetid: 0b83bd33-14d3-4611-8129-fccdae18053e
ms.openlocfilehash: efaef11cfdc036a201ced3357ca81b37a5dc29db
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619627"
---
# <a name="creating-the-dialog-resource"></a>Создание ресурса диалогового окна

Для проектирования [диалогового](dialog-boxes.md) окна и создания ресурса диалогового окна используется [Редактор диалоговых окон](../windows/dialog-editor.md). В редакторе диалоговых окон можно:

- Измените размер и расположение, когда появится диалоговое окно.

- Перетащите различные виды элементов управления из палитры элементов управления и поместите их там, где они нужны, в диалоговом окне.

- Расположите элементы управления с кнопками выравнивания на панели инструментов.

- Протестируйте диалоговое окно, имитируя внешний вид и поведение, которые он будет содержать в вашей программе. В тестовом режиме можно управлять элементами управления диалогового окна, вводя текст в текстовые поля, щелкая кнопки и т. д.

По завершении работы ресурс шаблона диалога будет сохранен в файле описания ресурсов приложения. При необходимости его можно изменить позже. Полное описание создания и изменения ресурсов диалоговых окон см. в разделах [редактора диалоговых окон](../windows/dialog-editor.md) . Этот метод также используется для создания ресурсов диалогового шаблона для классов [CFormView](reference/cformview-class.md) и [CRecordView](reference/crecordview-class.md) .

Когда вы намерены появление диалогового окна, создайте класс диалогового окна и сопоставьте его сообщения, как описано в разделе [Создание класса диалогового окна с помощью мастеров кода](creating-a-dialog-class-with-code-wizards.md).

## <a name="see-also"></a>См. также раздел

[Диалоговые окна](dialog-boxes.md)<br/>
[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
