---
title: Реализация окна с CWindowImpl
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: e5fdbf15ddd7edc69f0667a9b7e08c7c5e531a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319448"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Реализация окна с CWindowImpl

Для реализации окна, получить `CWindowImpl`класс из . В своем классе выводимых объявлений объявите карту сообщений и функции обработчика сообщений. Теперь вы можете использовать свой класс тремя различными способами:

- [Создание окна на основе нового класса Windows](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Суперкласс существующего класса Windows](#_atl_superclassing_an_existing_windows_class)

- [Подкласс существующего окна](#_atl_subclassing_an_existing_window)

## <a name="creating-a-window-based-on-a-new-windows-class"></a><a name="_atl_creating_a_window_based_on_a_new_windows_class"></a>Создание окна на основе нового класса Windows

`CWindowImpl`содержит [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) макрос для декларировать информацию о классе Windows. Этот макрос `GetWndClassInfo` реализует функцию, которая использует [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) для определения информации нового класса Windows. При `CWindowImpl::Create` вызове этот класс Windows регистрируется и создается новое окно.

> [!NOTE]
> `CWindowImpl`передает NULL `DECLARE_WND_CLASS` макросу, что означает, что ATL будет генерировать имя класса Windows. Чтобы указать свое имя, передайте `CWindowImpl`строку DECLARE_WND_CLASS в классе, полученном.

## <a name="example"></a>Пример

Ниже приводится пример класса, который реализует окно на основе нового класса Windows:

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Чтобы создать окно, создайте `CMyWindow` экземпляр, `Create` а затем вызовите метод.

> [!NOTE]
> Чтобы переопределить информацию о классе `GetWndClassInfo` Windows по умолчанию, `CWndClassInfo` реализуйте метод в своем производном классе, установив члены соответствующим значениям.

## <a name="superclassing-an-existing-windows-class"></a><a name="_atl_superclassing_an_existing_windows_class"></a>Суперклассирование существующего класса Windows

Макрос [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) позволяет создать окно, которое классифицировать существующий класс Windows. Укажите этот `CWindowImpl`макрос в классе выбытых. Как и любое другое окно ATL, сообщения обрабатываются картой сообщений.

При использовании DECLARE_WND_SUPERCLASS будет зарегистрирован новый класс Windows. Этот новый класс будет таким же, как и указанный `CWindowImpl::WindowProc` вами класс, но заменит процедуру окна (или с функцией, которая перекрывает этот метод).

## <a name="example"></a>Пример

Ниже приводится пример класса, который классирует стандартный класс edit:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Чтобы создать суперклассифицированное окно edit, `CMyEdit` создайте `Create` экземпляр, а затем вызовите метод.

## <a name="subclassing-an-existing-window"></a><a name="_atl_subclassing_an_existing_window"></a>Подклассирование существующего окна

Чтобы подклассифицировать существующее `CWindowImpl` окно, вывести класс из и объявить карту сообщений, как в двух предыдущих случаях. Обратите внимание, однако, что вы не указываете информацию о классе Windows, так как вы подклассифицируете уже существующее окно.

Вместо `Create`вызова, `SubclassWindow` вызова и передачи его ручку в существующее окно вы хотите подкласс. После того, как окно подклассно, оно будет использовать `CWindowImpl::WindowProc` (или функцию, которая перекрывает этот метод) для направления сообщений на карту сообщений. Чтобы отсоединить подклассифицированное окно `UnsubclassWindow`от объекта, позвоните. Затем будет восстановлена оригинальная процедура окна.

## <a name="see-also"></a>См. также раздел

[Реализация окна](../atl/implementing-a-window.md)
