---
title: Реализация диалогового окна
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 1a3084d4655e173234d3bb6e8d411b28e8968377
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263699"
---
# <a name="implementing-a-dialog-box"></a>Реализация диалогового окна

Существует два способа, чтобы диалоговое окно добавления в проект ATL: используйте мастер диалоговых окон ATL или добавьте его вручную.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>Добавление диалогового окна с мастер диалоговых окон ATL

В [диалоговое окно добавления класса](../ide/add-class-dialog-box.md), выберите объект диалогового окна ATL для добавления в проект ATL диалоговое окно. Заполните мастер диалоговых окон ATL соответствующим образом и нажмите кнопку **Готово**. Мастер добавляет класс, производный от [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) в проект. Откройте **представление ресурсов** из **представление** меню, диалоговое окно и дважды щелкните его, чтобы открыть его в редакторе ресурсов.

> [!NOTE]
>  Если диалоговое окно является производным от `CAxDialogImpl`, его можно разместить как ActiveX и элементов управления Windows. Если вы не хотите дополнительную нагрузку, связанную с поддержкой элементов управления ActiveX в классе диалогового окна, используйте [CSimpleDialog](../atl/reference/csimpledialog-class.md) или [CDialogImpl](../atl/reference/cdialogimpl-class.md) вместо этого.

Обработчики сообщений и событий можно добавить в класс диалогового окна из представления классов. Дополнительные сведения см. в разделе [Добавление обработчика сообщений ATL](../atl/adding-an-atl-message-handler.md).

## <a name="adding-a-dialog-box-manually"></a>Добавление диалогового окна вручную

Реализация диалогового окна похоже на реализация окна. Наследовать класс от либо [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), [CDialogImpl](../atl/reference/cdialogimpl-class.md), или [CSimpleDialog](../atl/reference/csimpledialog-class.md) и объявите [схему сообщений](../atl/message-maps-atl.md) для обработки сообщений. Тем не менее необходимо также указать идентификатор ресурса шаблона диалогового окна в производном классе. Ваш класс должен иметь член данных с именем `IDD` для хранения этого значения.

> [!NOTE]
>  При создании диалоговое окно, используя мастер диалоговых окон ATL, мастер автоматически добавляет `IDD` член как **перечисления** типа.

`CDialogImpl` позволяет реализовать модального или немодального диалогового окна, на котором размещены элементы управления Windows. `CAxDialogImpl` позволяет реализовать модального или немодального диалогового окна, на котором размещены элементы управления ActiveX и Windows.

Для создания модального диалогового окна, создайте экземпляр вашего `CDialogImpl`-производный (или `CAxDialogImpl`-производный) класса, а затем вызвать [DoModal](../atl/reference/cdialogimpl-class.md#domodal) метод. Чтобы закрыть модальное диалоговое окно, вызовите [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) метод из обработчика сообщений. Для создания немодального диалогового окна, вызовите [создать](../atl/reference/cdialogimpl-class.md#create) вместо метода `DoModal`. Для уничтожения немодального диалогового окна, вызовите [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow).

Получение событий выполняется автоматически в [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md). Реализовать обработчики сообщений диалогового окна, как это делается, чтобы обработчики в `CWindowImpl`-производного класса. Если возвращаемое значение конкретного сообщения, вернуть его как `LRESULT`. Возвращенный `LRESULT` значения сопоставляются с ATL для правильной обработки диспетчером диалоговое окно Windows. Дополнительные сведения см. в статье исходный код для [CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) в atlwin.h.

## <a name="example"></a>Пример

Следующий класс реализует диалоговое окно:

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>См. также

[Классы окон](../atl/atl-window-classes.md)
