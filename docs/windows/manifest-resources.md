---
title: Ресурсы манифеста (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
ms.openlocfilehash: 081fd12a86c31973c7856ca7b9f3fcb129e2eb81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578286"
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

Чтобы узнать версию и введите сведения, содержащиеся в ресурсе манифеста, можно открыть файл в средстве просмотра XML или в текстовом редакторе Visual Studio. Дополнительные сведения см. в статье [Открытие ресурса манифеста в текстовом редакторе Visual Studio](../windows/how-to-open-a-manifest-resource.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="limitations"></a>Ограничения

Допускается иметь только один ресурс манифеста на каждый модуль.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления](../mfc/controls-mfc.md)<br/>
[Работа с файлами ресурсов](../windows/working-with-resource-files.md)