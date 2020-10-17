---
title: Реализация окна с помощью Квиндовимпл
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: 7ce1a2ec08e49e047aee5248bda0094d9e392614
ms.sourcegitcommit: ced5ff1431ffbd25b20d106901955532723bd188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "92135519"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Реализация окна с помощью Квиндовимпл

Чтобы реализовать окно, создайте класс, производный от `CWindowImpl` . В производном классе Объявите схему сообщений и функции обработчика сообщений. Теперь класс можно использовать тремя разными способами:

- [Создание окна на основе нового класса Windows](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Суперкласс для существующего класса Windows](#_atl_superclassing_an_existing_windows_class)

- [Подкласс существующего окна](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Создание окна на основе нового класса Windows

`CWindowImpl` содержит макрос [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) для объявления сведений о классе Windows. Этот макрос реализует `GetWndClassInfo` функцию, которая использует [квндклассинфо](../atl/reference/cwndclassinfo-class.md) для определения информации о новом классе Windows. Когда `CWindowImpl::Create` вызывается, этот класс Windows регистрируется, и создается новое окно.

> [!NOTE]
> `CWindowImpl` передает в макрос значение NULL `DECLARE_WND_CLASS` , означающее, что ATL создаст имя класса Windows. Чтобы указать собственное имя, передайте строку в DECLARE_WND_CLASS в `CWindowImpl` классе, производном от.

## <a name="example-implement-a-window"></a>Пример. Реализация окна

Ниже приведен пример класса, реализующего окно на основе нового класса Windows:

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Чтобы создать окно, создайте экземпляр, `CMyWindow` а затем вызовите `Create` метод.

> [!NOTE]
> Чтобы переопределить сведения о классе Windows по умолчанию, реализуйте `GetWndClassInfo` метод в производном классе, установив `CWndClassInfo` для элементов соответствующие значения.

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a> Подклассировать существующий класс Windows

Макрос [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) позволяет создать окно, которое будет являться классом существующего класса Windows. Укажите этот макрос в `CWindowImpl` классе, производном от. Как и любое другое окно ATL, сообщения обрабатываются схемой сообщений.

При использовании DECLARE_WND_SUPERCLASS будет зарегистрирован новый класс Windows. Этот новый класс будет таким же, как и существующий указанный вами класс, но заменит процедуру окна на `CWindowImpl::WindowProc` (или с помощью функции, переопределяющей этот метод).

## <a name="example-superclass-the-edit-class"></a>Пример: суперкласс для класса Edit

Ниже приведен пример класса, который является классом стандартного класса Edit.

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Чтобы создать окно редактирования с помощью класса, создайте экземпляр класса `CMyEdit` и вызовите `Create` метод.

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a> Подклассировать существующее окно

Чтобы создать подкласс для существующего окна, создайте класс, производный от класса, `CWindowImpl` и объявите схему сообщения, как в двух предыдущих случаях. Однако обратите внимание, что не нужно указывать сведения о классе Windows, так как вы будете подклассировать уже существующее окно.

Вместо вызова `Create` , вызовите `SubclassWindow` и передайте ему обработчик в существующее окно, которое нужно подкласс. После создания подкласса для окна он будет использовать `CWindowImpl::WindowProc` (или функцию, переопределяющую этот метод), чтобы направить сообщения на схему сообщений. Чтобы отключить окно с подклассом из объекта, вызовите `UnsubclassWindow` . После этого будет восстановлена исходная процедура окна.

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)
