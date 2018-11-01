---
title: 'Как: копирование ресурсов (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 6baa53f8a047a8a7fc7540234dc0be2e08476d9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545103"
---
# <a name="how-to-copy-resources-c"></a>Как: копирование ресурсов (C++)

Можно скопировать ресурсы из одного файла в другой без изменений или вы можете [изменение языка или условий использования ресурса в процессе копирования его](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).

Можно легко скопировать ресурсы из существующего ресурса или исполняемого файла в текущий файл ресурсов. Чтобы сделать это, откройте оба файла, которая содержит ресурсы, в то же время и перетащите элементы из одного файла в другой, или скопируйте и вставьте между двумя файлами. Этот метод работает для RC-файлов ресурсов и файлов ресурсов (.rct) шаблона, а также исполняемых файлов (.exe).

> [!NOTE]
> Visual C++ содержит примеры файлов ресурсов, которые можно использовать в приложении. Дополнительные сведения см. в разделе [CLIPART: общие ресурсы](https://github.com/Microsoft/VCSamples).

Можно использовать метод перетаскивания и вставки между RC-файлов, открытых [вне проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>Копирование ресурсов между файлами с помощью метода перетаскивания и вставки

1. Откройте отдельно два файла ресурсов (Дополнительные сведения см. в разделе [Просмотр ресурсов в .rc файле за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Например, откройте Source1.rc и Source2.rc.

2. В первом RC-файле выберите ресурс, который требуется скопировать. Например, в `Source1.rc`, нажмите кнопку **IDD_DIALOG1**.

3. Удерживайте нажатой клавишу CTRL и перетащите ресурс во втором RC-файл. Например, перетащите **IDD_DIALOG1** из `Source1.rc` для `Source2.rc`.

   > [!NOTE]
   > Перетаскивание ресурса без удерживания нажатой **Ctrl** перемещает ключ ресурса, а не копируя его.

### <a name="to-copy-resources-using-copy-and-paste"></a>Для копирования ресурсов с помощью копирования и вставки

1. Откройте отдельно два файла ресурсов (Дополнительные сведения см. в разделе [Просмотр ресурсов в .rc файле за пределами проекта](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Например, Source1.rc и Source2.rc.

2. В исходном файле, из которого вы хотите скопировать ресурс (например, `Source1.rc`), щелкните ресурс правой кнопкой мыши и выберите пункт **копирования** в контекстном меню.

3. Щелкните правой кнопкой мыши файл ресурсов, в которую вы хотите добавить ресурс (например, `Source2.rc`). Выберите **вставить** в контекстном меню.

   > [!NOTE]
   > Вам не удается перетащите, копирование, вырезание или вставки между файлами ресурсов в проект (**представление ресурсов**) и автономный RC-файлов, (которые open в окнах документов). Это можно сделать в предыдущих версиях продукта.

   > [!NOTE]
   > Во избежание конфликтов с именами и значениями в существующем файле Visual C++ может изменить значение символа копируемого ресурса или имя и значение, при копировании в новый файл.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Практическое руководство. Открытие файла описания ресурсов за пределами проекта (в автономном режиме)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
[Файлы ресурсов](../windows/resource-files-visual-studio.md)<br/>
[Редакторы ресурсов](../windows/resource-editors.md)