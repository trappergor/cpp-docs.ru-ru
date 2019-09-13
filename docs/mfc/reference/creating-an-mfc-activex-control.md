---
title: Создание элемента управления ActiveX MFC
ms.date: 08/19/2019
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: d35b788910b0c73a3b6da85faf119958ffbccea0
ms.sourcegitcommit: bf1940a39029dbbd861f95480f55e5e8bd25cda0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2019
ms.locfileid: "70108445"
---
# <a name="creating-an-mfc-activex-control"></a>Создание элемента управления ActiveX MFC

Программы элементов управления ActiveX — это модульные программы, предназначенные для предоставления конкретного типа функциональности родительскому приложению. Например, можно создать такой элемент управления, как кнопка для использования в диалоговом окне, или панель инструментов для использования на веб-странице.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которую не следует использовать для новой разработки. Дополнительные сведения см. в разделе [элементы управления ActiveX](../activex-controls.md).

Самый простой способ создать элемент управления ActiveX MFC — использовать [Мастер элементов ActiveX MFC](../../mfc/reference/mfc-activex-control-wizard.md).

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>Создание элемента управления ActiveX MFC с помощью мастера элементов ActiveX MFC

1. Следуйте инструкциям в разделе справки по [созданию приложения MFC](creating-an-mfc-application.md) , но выберите **элемент ActiveX MFC** в списке доступных шаблонов.

1. Определите [Параметры приложения](../../mfc/reference/application-settings-mfc-activex-control-wizard.md), [имена элементов управления](../../mfc/reference/control-names-mfc-activex-control-wizard.md)и [Параметры управления](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) с помощью мастера элементов ActiveX MFC.

    > [!NOTE]
    >  Для сохранения параметров, заданных в мастере по умолчанию, пропустите этот шаг.

1. Нажмите кнопку **Готово** для завершения работы мастера и откройте новый проект в среде разработки.

После создания проекта можно просмотреть файлы, созданные в **Обозреватель решений**. Дополнительные сведения о файлах, создаваемых мастером для проекта, см. в созданном для проекта файле ReadMe.txt. Дополнительные сведения о типах файлов см. в разделе [Типы файлов, создаваемых для проектов Visual Studio C++](../../build/reference/file-types-created-for-visual-cpp-projects.md).

После создания проекта можно использовать мастера кода для добавления [функций](../../ide/add-member-function-wizard.md), [переменных](../../ide/add-member-variable-wizard.md), [событий](../../ide/add-event-wizard.md), [свойств](../../ide/names-add-property-wizard.md)и [методов](../../ide/add-method-wizard.md). Дополнительные сведения о настройке элемента управления ActiveX см. в разделе [элементы управления ActiveX в MFC](../../mfc/mfc-activex-controls.md).

## <a name="see-also"></a>См. также

[Добавление функциональных возможностей с помощью мастеров кода](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Страницы свойств](../../build/reference/property-pages-visual-cpp.md)

