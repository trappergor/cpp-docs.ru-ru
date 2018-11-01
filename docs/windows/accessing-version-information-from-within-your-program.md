---
title: Доступ к сведениям о версии из создаваемой программы (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.version
helpviewer_keywords:
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
ms.openlocfilehash: 028ea6126b75b914e7ff9a4ded2d08efa9d35b28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644630"
---
# <a name="accessing-version-information-from-within-your-program-c"></a>Доступ к сведениям о версии из создаваемой программы (C++)

### <a name="to-access-version-information-from-within-your-program"></a>Доступ к сведениям о версии из создаваемой программы

1. Если нужно получить доступ к сведениям о версии из создаваемой программы, используйте функции [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) и [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) .

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор сведений о версии](../windows/version-information-editor.md)<br/>
[Сведения о версии (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)