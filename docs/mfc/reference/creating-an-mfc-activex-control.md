---
title: Создание элемента управления ActiveX MFC
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: 031c8596e568f01cdecd7139d959a77923c341eb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294958"
---
# <a name="creating-an-mfc-activex-control"></a>Создание элемента управления ActiveX MFC

Программы управления ActiveX являются модульные программы, разработанные для предоставления определенной функциональности в родительское приложение. Например можно создать элемент управления, например кнопки для использования в диалоговом окне или панели инструментов для использования на веб-странице.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения см. в разделе [элементы управления ActiveX](../activex-controls.md).

Самый простой способ создания элемента управления MFC ActiveX является использование [мастер элементов управления ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md).

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>Для создания элемента управления ActiveX MFC, с помощью мастера элементов управления ActiveX MFC

1. Следуйте инструкциям, приведенным в разделе справки [Создание проекта с использованием мастера приложений Visual C++](../../ide/creating-desktop-projects-by-using-application-wizards.md).

1. В **новый проект** выберите **элемента управления ActiveX MFC** значок в области «Шаблоны», чтобы открыть мастер элементов управления ActiveX MFC.

1. Определение вашего [параметры приложения](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [имена элементов управления](../../mfc/reference/control-names-mfc-activex-control-wizard.md), и [управлять параметрами](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) с помощью мастера элементов управления ActiveX MFC.

    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.

1. Нажмите кнопку **Готово** закрыть мастер и открыть проект в среде разработки.

После создания проекта можно просмотреть файлы, созданные в **обозревателе решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [типы файлов, создаваемых для проектов Visual C++](../../ide/file-types-created-for-visual-cpp-projects.md).

После создания проекта, можно использовать мастеры кода для добавления [функции](../../ide/add-member-function-wizard.md), [переменных](../../ide/add-member-variable-wizard.md), [события](../../ide/add-event-wizard.md), [свойства](../../ide/names-add-property-wizard.md), и [методы](../../ide/add-method-wizard.md). Дополнительные сведения о настройке элементов управления ActiveX, см. в разделе [элементы ActiveX в MFC](../../mfc/mfc-activex-controls.md).

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Страницы свойств](../../ide/property-pages-visual-cpp.md)
