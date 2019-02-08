---
title: Ресурсы манифеста (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
- resources [C++], opening
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
ms.openlocfilehash: 2d135cb2d512313f107eef7e95ec90d7972b68b4
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850194"
---
# <a name="manifest-resources-c"></a>Ресурсы манифеста (C++)

В проектах классических приложений C++ ресурсы манифеста — это XML-файлы, описывающие зависимости, которые использует приложение. Например, в Visual Studio файл манифеста, созданный мастером MFC, определяет, какие версии библиотек DLL общих элементов управления Windows (5.0 или 6.0), приложение должно использовать:

```xml
<description>Your app description here</description>
<dependency>
    <dependentAssembly>
        <assemblyIdentity
            type="win32"
            name="Microsoft.Windows.Common-Controls"
            version="6.0.0.0"
            processorArchitecture="X86"
            publicKeyToken="6595b64144ccf1df"
            language="*"
        />
    </dependentAssembly>
</dependency>
```

Для приложений Windows XP и Windows Vista ресурс манифеста не только определяет, что приложение должно использовать последнюю версию общих элементов управления Windows (версии 6.0, см. выше), но также поддерживает [элемент управления Syslink](/windows/desktop/Controls/syslink-overview).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

Чтобы узнать версию и введите сведения, содержащиеся в ресурсе манифеста, можно открыть файл в средстве просмотра XML или в текстовом редакторе Visual Studio. Если вы откроете ресурс манифеста из [представления ресурсов](../windows/resource-view-window.md), этот ресурс откроется в двоичном формате. Чтобы просмотреть содержимое ресурса манифеста в более удобном формате, необходимо открыть ресурс из **обозревателе решений**.

## <a name="to-open-a-manifest-resource-in-the-text-editor"></a>Открытие ресурса манифеста в текстовом редакторе

1. Открыв проект в **обозревателе решений**, разверните **файлы ресурсов** папки.

1. Дважды щелкните файл с расширением MANIFEST.

   Ресурс манифеста откроется в **текстовый редактор**.

## <a name="to-open-a-manifest-resource-in-another-editor"></a>Открытие ресурса манифеста в другом редакторе

1. В **обозревателе решений**, щелкните правой кнопкой мыши файл с расширением MANIFEST и выберите **открыть с помощью...**  в контекстном меню.

1. В **открыть с помощью** диалоговом окне выберите редактор, который вы хотите использовать и выберите **откройте**.

## <a name="limitations"></a>Ограничения

Допускается иметь только один ресурс манифеста на каждый модуль.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления](../mfc/controls-mfc.md)<br/>
[Работа с файлами ресурсов](../windows/working-with-resource-files.md)