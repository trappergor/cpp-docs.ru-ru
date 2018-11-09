---
title: Добавление класса из элемента управления ActiveX (Visual C++)
ms.date: 09/07/2018
helpviewer_keywords:
- ActiveX controls [C++], adding classes
- classes [C++], creating
ms.assetid: 729fcb37-54b8-44d5-9b4e-50bb16e0eea4
ms.openlocfilehash: c78919aeee2d2577cd7371952d95c57c17b1e5ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466629"
---
# <a name="adding-a-class-from-an-activex-control-visual-c"></a>Добавление класса из элемента управления ActiveX (Visual C++)

Этот мастер используется для создания класса MFC из интерфейса в доступном элементе управления ActiveX. Вы можете добавить класс MFC для [приложения MFC](../mfc/reference/creating-an-mfc-application.md), [библиотеки DLL MFC](../mfc/reference/creating-an-mfc-dll-project.md) или [элемента управления ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md).

> [!WARNING]
> В Visual Studio 2017 версии 15.9 этот мастер кода является нерекомендуемым и будет удален из будущей версии Visual Studio. Этот мастер используется редко. Удаление этого мастера не влияет на общую поддержку для ATL и MFC. Если вы хотите поделиться своим мнением об устаревании этого мастера, пройдите [этот опрос](https://www.surveymonkey.com/r/QDWKKCN). Ваше мнение важно для нас.

> [!NOTE]
>  Чтобы добавить класс из элемента управления ActiveX, вам не нужно создавать проект MFC с включенной автоматизацией.

Элемент управления ActiveX — это многоразовый программный компонент, основанный на модели COM, который поддерживает широкий набор функциональных возможностей OLE и может быть настроен под различные потребности программного обеспечения. Элементы управления ActiveX предназначены для использования в обычных контейнерах элементов управления ActiveX, а также на веб-страницах в Интернете.

### <a name="to-add-an-mfc-class-from-an-activex-control"></a>Добавление класса MFC из элемента управления ActiveX

1. В **обозревателе решений** или [представлении классов](/visualstudio/ide/viewing-the-structure-of-code) щелкните правой кнопкой мыши имя проекта, куда вы хотите добавить класс элемента управления ActiveX.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.

1. В области "Шаблоны" диалогового окна [Добавление класса](../ide/add-class-dialog-box.md) щелкните **Класс MFC из элемента управления ActiveX**, а затем нажмите кнопку **Открыть**, чтобы отобразить [Мастер добавления классов из элемента ActiveX](../ide/add-class-from-activex-control-wizard.md).

В этом мастере можно добавить несколько интерфейсов в элементе управления ActiveX. Аналогично можно создать классы из более чем одного элемента управления ActiveX в одном сеансе мастера.

Вы можете добавлять классы из элементов управления ActiveX, зарегистрированных в системе, а также расположенных в файлах библиотеки типов (TLB, OLB, DLL, OCX или EXE) без их предварительной регистрации в системе. Дополнительные сведения о регистрации элементов управления ActiveX см. в разделе [Регистрация элементов управления OLE](../mfc/reference/registering-ole-controls.md).

Мастер создает класс MFC, производный от [CWnd](../mfc/reference/cwnd-class.md) или [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md), для каждого интерфейса, добавляемого из выбранного элемента управления ActiveX.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br>
[Введение в модель COM и ATL](../atl/introduction-to-com-and-atl.md)