---
title: Строки, мастер страницы свойств ATL
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.strings
helpviewer_keywords:
- ATL Property Page Wizard, strings
ms.assetid: 00547db6-911f-49eb-92e1-2ba67079d4df
ms.openlocfilehash: 61378e0aa2cee94420849195a94203be078418ff
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921117"
---
# <a name="strings-atl-property-page-wizard"></a>Строки, мастер страницы свойств ATL

::: moniker range="msvc-160"

Мастер страницы свойств в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="<=msvc-150"

Предоставляет текст, связанный со страницей свойств.

- **Заголовок**

   Задает текст, отображаемый для вкладки на странице свойств.

- **Строка документа**

   Задает текстовую строку, описывающую страницу. Эта строка может отображаться в диалоговом окне страницы свойств. Фрейм свойства может использовать описание в строке состояния или в подсказке. Стандартный фрейм свойства в настоящее время не использует эту строку.

- **Файл справки**

   Задает имя файла справки, в котором описывается использование страницы свойств. Это имя не должно содержать путь. Когда пользователь нажимает кнопку **Справка** , фрейм открывает файл справки в каталоге, указанном в значении ключа HelpDir в записях реестра страницы свойств в разделе идентификатора CLSID.

::: moniker-end

## <a name="see-also"></a>См. также статью

[Мастер страницы свойств ATL](../../atl/reference/atl-property-page-wizard.md)<br/>
[Параметры, мастер страниц свойств ATL](../../atl/reference/options-atl-property-page-wizard.md)
