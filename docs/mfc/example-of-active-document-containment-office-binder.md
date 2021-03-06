---
title: Пример вложения активного документа. Office Binder
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- examples [MFC], active document containment
- containers [MFC], active document
- active document containers [MFC], examples
- Office Binder [MFC]
- MFC COM, active document containment
ms.assetid: 70dd8568-e8bc-44ac-bf5e-678767efe8e3
ms.openlocfilehash: fe9ccb5b78d9a60c5b8b2a19fe0818a8e1682f00
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623124"
---
# <a name="example-of-active-document-containment-office-binder"></a>Пример вложения активного документа. Office Binder

Microsoft Office связыватель является примером активного контейнера документа. Связыватель Office включает две основные панели, как правило, в качестве контейнеров. Левая панель содержит значки, соответствующие активным документам в связывателе. Каждый документ называется *разделом* в связывателе. Например, связыватель может содержать документы Word, файлы PowerPoint, электронные таблицы Excel и т. д.

При щелчке значка в левой области активируется соответствующий активный документ. На правой панели подшивки отображается содержимое текущего выбранного активного документа.

Если открыть и активировать документ Word в связывателе, в верхней части рамки представления появится строка меню и панели инструментов, а содержимое документа можно изменить с помощью любой команды или инструмента Word. Однако строка меню является сочетанием строк меню связывателя и Word. Так как связыватель и Word имеют меню **справки** , содержимое соответствующих меню объединяется. Контейнеры активных документов, такие как Office BINDER, автоматически обеспечивают слияние меню **справки** . Дополнительные сведения см. в разделе [Слияние меню "Справка](help-menu-merging.md)".

При выборе активного документа другого типа приложение интерфейс связывателя изменяется в соответствии с типом приложения активного документа. Например, если связыватель содержит электронную таблицу Excel, вы увидите, что меню в связывателе изменится при выборе раздела электронной таблицы Excel.

Есть, конечно же, другие возможные типы контейнеров рядом с связывателями. В проводнике используется стандартный интерфейс двойной панели, в котором в левой области используется элемент управления "дерево" для отображения иерархического списка каталогов на диске или в сети, в то время как на правой панели отображаются файлы, содержащиеся в выбранном в данный момент каталоге. Тип веб-браузера (например, Microsoft Internet Explorer), вместо использования сдвоенного интерфейса обычно имеет один кадр и обеспечивает навигацию с помощью гиперссылок.

## <a name="see-also"></a>См. также раздел

[Вложение активного документа](active-document-containment.md)
