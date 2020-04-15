---
title: Реализация dialog Box
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 435926b0a0affde03580ceb2b479cb08a17d0454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319477"
---
# <a name="implementing-a-dialog-box"></a>Реализация dialog Box

Есть два способа добавить диалоговую коробку к вашему проекту ATL: используйте ATL Dialog Wizard или добавляйте его вручную.

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>Добавление Dialog Box с atL Dialog Мастер

В [диалоговом поле Add Class](../ide/add-class-dialog-box.md)выберите объект ATL Dialog, чтобы добавить диалоговый ящик в свой проект ATL. Заполните ATL Dialog Мастер по мере необходимости и нажмите **Закончить**. Мастер добавляет в ваш проект класс, полученный из [CAxDialogImpl.](../atl/reference/caxdialogimpl-class.md) Откройте **вид ресурсов** из меню **View,** найдите диалог и дважды щелкните его, чтобы открыть его в редакторе ресурса.

> [!NOTE]
> Если ваш диалоговый `CAxDialogImpl`ящик получен из, он может принимать элементы управления ActiveX и Windows. Если вы не хотите накладные расходы поддержки управления ActiveX в вашем классе диалоговых коробок, используйте [CSimpleDialog](../atl/reference/csimpledialog-class.md) или [CDialogImpl](../atl/reference/cdialogimpl-class.md) вместо этого.

Обработчики сообщений и событий могут быть добавлены в класс диалогов из класса View. Для получения дополнительной информации [см.](../atl/adding-an-atl-message-handler.md)

## <a name="adding-a-dialog-box-manually"></a>Добавление dialog Box вручную

Реализация диалогового окна аналогична реализации окна. Вы получаете класс от [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), [CDialogImpl](../atl/reference/cdialogimpl-class.md), или [CSimpleDialog](../atl/reference/csimpledialog-class.md) и объявить [карту сообщений](../atl/message-maps-atl.md) для обработки сообщений. Однако необходимо также указать идентификатор ресурсов шаблона диалогов в своем классе. Ваш класс должен иметь `IDD` член данных, призванный удерживать это значение.

> [!NOTE]
> При создании диалогового окна с помощью ATL Dialog `IDD` Wizard мастер автоматически добавляет его в тип **enum.**

`CDialogImpl`позволяет реализовать модальный или бесрежимный диалоговый ящик, в котором размещается управление Windows. `CAxDialogImpl`позволяет реализовать модальный или бесрежимный диалоговой ящик, в котором размещается как управление ActiveX, так и Windows.

Чтобы создать модальный диалоговый ящик, создайте экземпляр вашего `CDialogImpl`-производного (или `CAxDialogImpl`-производного) класса, а затем вызовите метод [DoModal.](../atl/reference/cdialogimpl-class.md#domodal) Чтобы закрыть модульное поле диалогов, позвоните в метод [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) от обработчика сообщений. Чтобы создать бесрежимное диалоговое окно, позвоните в метод [«Создание»](../atl/reference/cdialogimpl-class.md#create) вместо `DoModal`. Чтобы уничтожить бесрежимный диалоговый ящик, позвоните [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow).

Тонущие события автоматически выполняются в [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md). Реализация обработчиков сообщений диалогового окна по `CWindowImpl`мере того, как обработчики в классе производных. Если есть значение возврата, конкретное сообщение, `LRESULT`верните его в качестве . Возвратные `LRESULT` значения отображаются ATL для правильной обработки менеджером диалога Windows. Для получения подробной информации смотрите исходный код [cDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) в atlwin.h.

## <a name="example"></a>Пример

Следующий класс реализует диалоговую коробку:

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>См. также раздел

[Классы окон](../atl/atl-window-classes.md)
