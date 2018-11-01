---
title: Реализация окна с помощью CWindowImpl
ms.date: 11/04/2016
f1_keywords:
- CWindowImpl
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
ms.openlocfilehash: f9286598184cfb12c415de637fccc07011369fd5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501963"
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Реализация окна с помощью CWindowImpl

Чтобы реализовать окна, являются производными от класса `CWindowImpl`. В производном классе объявите схему сообщений и функций обработчиков сообщений. Теперь можно использовать класс тремя разными способами:

- [Создать окно, в зависимости от нового класса Windows](#_atl_creating_a_window_based_on_a_new_windows_class)

- [Суперкласс существующий класс Windows](#_atl_superclassing_an_existing_windows_class)

- [Подкласс существующему окну](#_atl_subclassing_an_existing_window)

##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> Создание окна на основе нового класса Windows

`CWindowImpl` содержит [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) макрос для объявления сведения о классе Windows. Реализует этот макрос `GetWndClassInfo` функцию, которая использует [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) задать сведения о нового класса Windows. Когда `CWindowImpl::Create` вызывается этот Windows класс регистрируется и создается новое окно.

> [!NOTE]
>  `CWindowImpl` передает значение NULL, чтобы `DECLARE_WND_CLASS` макросом, который означает, что ATL создаст имя класса Windows. Чтобы указать собственное имя, передать строку DECLARE_WND_CLASS в вашей `CWindowImpl`-производного класса.

## <a name="example"></a>Пример

Ниже приведен пример класса, который реализует окно, в зависимости от нового класса Windows.

[!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]

Чтобы создать окно, создайте экземпляр `CMyWindow` , а затем вызвать `Create` метод.

> [!NOTE]
>  Чтобы переопределить сведения о классе Windows по умолчанию, реализовать `GetWndClassInfo` метод в производном классе, задав `CWndClassInfo` участникам соответствующие значения.

##  <a name="_atl_superclassing_an_existing_windows_class"></a> Создание надклассов существующий класс Windows

[DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) макрос позволяет создать окно, является суперклассом существующих Windows класса. Укажите этот макрос в вашей `CWindowImpl`-производного класса. Как и любое другое окно ATL сообщения обрабатываются виртуальной схемы сообщений.

При использовании DECLARE_WND_SUPERCLASS будет зарегистрирован новый класс Windows. Этот новый класс будет совпадать с именем существующего класса, указать, но приведет к замене процедуру окна с `CWindowImpl::WindowProc` (или функцией, который переопределяет этот метод).

## <a name="example"></a>Пример

Следуя приведен пример класса, является суперклассом стандартный изменить класс:

[!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]

Чтобы создать суперкласса окно редактирования, создайте экземпляр `CMyEdit` , а затем вызвать `Create` метод.

##  <a name="_atl_subclassing_an_existing_window"></a> Создание подкласса существующему окну

Подкласс существующему окну, являются производными от класса `CWindowImpl` и объявите схему сообщений, как и в предыдущих двух случаях. Тем не менее, не указать любые сведения о классе в Windows, так как подкласс будет уже существующему окну.

Вместо вызова метода `Create`, вызовите `SubclassWindow` и передать его дескриптор в открытом окне, необходимо создать подкласс. Если окно является подклассом, он будет использовать `CWindowImpl::WindowProc` (или функцию, который переопределяет этот метод) для направления сообщений в схеме сообщений. Чтобы отсоединить выведенных в подклассы окна из объекта, вызовите `UnsubclassWindow`. Будет восстановлена окна исходную процедуру окна.

## <a name="see-also"></a>См. также

[Реализация окна](../atl/implementing-a-window.md)

