---
title: Манифест ресурсов (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifest resources [C++]
- resources [C++], manifest
ms.assetid: 8615334c-22a0-44c0-93e0-5924528c9917
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2da93d1baaf95799c7ef68d6cc854d554fbe6c47
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429569"
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

Для приложений Windows XP или Windows Vista ресурс манифеста не только определяет приложение использовать последнюю версию общих элементов управления Windows (версии 6.0, см. выше), но также поддерживает [управления Syslink](/windows/desktop/Controls/syslink-overview).

Чтобы узнать версию и введите сведения, содержащиеся в ресурсе манифеста, можно открыть файл в средстве просмотра XML или в текстовом редакторе Visual Studio. Дополнительные сведения см. в статье [Открытие ресурса манифеста в текстовом редакторе Visual Studio](../windows/how-to-open-a-manifest-resource.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*.

## <a name="limitations"></a>Ограничения

Допускается иметь только один ресурс манифеста на каждый модуль.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Элементы управления](../mfc/controls-mfc.md)<br/>
[Работа с файлами ресурсов](../windows/working-with-resource-files.md)