---
title: "Реализация окна с CWindowImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CWindowImpl
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing, ATL
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80aca6af847a33fd7217d0ad710c928f6d2ca32e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-window-with-cwindowimpl"></a>Реализация окна с CWindowImpl
Чтобы реализовать окна, создайте класс, производный от `CWindowImpl`. В производном классе объявите схему сообщений и функций обработчиков сообщений. Теперь можно использовать класс тремя разными способами:  
  
-   [Создать окно на основе нового класса Windows](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [Суперкласса существующего класса Windows](#_atl_superclassing_an_existing_windows_class)  
  
-   [Подкласс существующему окну](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a>Создание окна на основе нового класса Windows  
 `CWindowImpl`содержит [DECLARE_WND_CLASS](reference/window-class-macros.md#declare_wnd_class) макрос для объявления сведения о классе Windows. Реализует этот макрос `GetWndClassInfo` функции, которая использует [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) задать сведения о класса Windows. Когда `CWindowImpl::Create` вызывается эта Windows класс регистрируется и создается новое окно.  
  
> [!NOTE]
>  `CWindowImpl`передает **NULL** для `DECLARE_WND_CLASS` макросом, который означает ATL создаст имя класса Windows. Чтобы задать собственное имя, передайте строку для `DECLARE_WND_CLASS` в ваш `CWindowImpl`-производного класса.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример класса, который реализует окно на основе нового класса Windows:  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_1.h)]  
  
 Для создания окна, создайте экземпляр `CMyWindow` и затем вызвать **создать** метод.  
  
> [!NOTE]
>  Чтобы переопределить информация о классе Windows по умолчанию, реализовать `GetWndClassInfo` метод в производном классе, задав `CWndClassInfo` членами с соответствующими значениями.  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a>Создание суперклассов существующего класса Windows  
 [DECLARE_WND_SUPERCLASS](reference/window-class-macros.md#declare_wnd_superclass) макрос позволяет создать окно, существующими Windows является суперклассом класса. Укажите этот макрос в вашей `CWindowImpl`-производного класса. Как и любое другое окно ATL сообщения обрабатываются схему сообщений.  
  
 При использовании `DECLARE_WND_SUPERCLASS`, новый класс Windows будет зарегистрирована. Этот новый класс будет совпадать с именем существующего класса можно указать, но приведет к замене процедуру окна с `CWindowImpl::WindowProc` (или функцией, которая переопределяет этот метод).  
  
## <a name="example"></a>Пример  
 Следуя приведен пример класса, является суперклассом Стандартная редактирования класса:  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/cpp/implementing-a-window-with-cwindowimpl_2.h)]  
  
 Чтобы создать суперкласса окна редактора, создайте экземпляр `CMyEdit` и затем вызвать **создать** метод.  
  
##  <a name="_atl_subclassing_an_existing_window"></a>Создание подклассов существующему окну  
 Подкласс существующему окну, создайте класс, производный от `CWindowImpl` и объявите схему сообщений, как показано в двух предыдущих случаев. Тем не менее, не указан класс сведений о Windows, так как подкласс будет уже существующему окну.  
  
 Вместо вызова метода **создать**, вызовите `SubclassWindow` и передать его дескриптор существующего необходимо создать подкласс окна. Если окно является подклассом, он будет использовать `CWindowImpl::WindowProc` (или на функцию, который переопределяет этот метод) для направления сообщений в схему сообщений. Чтобы отсоединить подклассов окна из объекта, вызовите `UnsubclassWindow`. В окне исходной процедуры окна будет восстановлена.  
  
## <a name="see-also"></a>См. также  
 [Реализация окна](../atl/implementing-a-window.md)

