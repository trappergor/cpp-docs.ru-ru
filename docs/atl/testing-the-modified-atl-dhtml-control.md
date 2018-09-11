---
title: Тестирование элемента управления DHTML в ATL измененный | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9730f8ef9bfc89d65ffb89ddbbfe67ce247138e9
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755607"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>Тестирование элемента управления измененный DHTML в ATL

Испытайте новый элемент управления для просмотра их работу.

#### <a name="to-build-and-test-the-modified-control"></a>Построение и тестирование измененного элемента управления

1. Перестройте проект и откройте его в тестовом контейнере. См. в разделе [тестирование свойств и событий с использованием тестового контейнера](../mfc/testing-properties-and-events-with-test-container.md) сведения о том, как получить доступ к контейнеру теста.

     Размер элемента управления для отображения всех кнопок, вы добавили.

2. Изучите две кнопки, которые были вставлены путем изменения HTML-код. Каждой кнопки есть метки, определенного в [изменение элемента управления ATL DHTML](../atl/modifying-the-atl-dhtml-control.md): **обновить** и **HelloHTML**.

3. Протестируйте две новые кнопки, чтобы увидеть, как они работают.

Теперь можно проверьте методы, которые не являются частью пользовательского интерфейса.

1. Выделите элемент управления, чтобы активировать границы.

2. На **управления** меню, щелкните **вызов методов**.

Методы в списке с меткой **имя метода** приведены методы, которые могут вызывать контейнера: `MethodInvoked` и `GoToURL`. Все остальные методы управляются пользовательского интерфейса.

1. Выберите метод для вызова, а затем нажмите кнопку `Invoke` Отображение окна сообщения метода или для перехода к www.microsoft.com.

2. В **вызов методов** диалоговом окне щелкните **закрыть**.

Дополнительные сведения о различных элементов и файлов, составляющих элемент управления DHTML в ATL, см. в разделе [определение элементов для проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md).

## <a name="see-also"></a>См. также

[Поддержка элементов управления DHTML](../atl/atl-support-for-dhtml-controls.md)

