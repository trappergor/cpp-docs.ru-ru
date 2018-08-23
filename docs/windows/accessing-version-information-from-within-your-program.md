---
title: Доступ к сведениям о версии из создаваемой программы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.version
dev_langs:
- C++
helpviewer_keywords:
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 18622333-d9e8-4309-9465-677cd10c79b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db32214543278023cdce91654c86e53568fffb00
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606926"
---
# <a name="accessing-version-information-from-within-your-program"></a>Доступ к сведениям о версии из создаваемой программы

### <a name="to-access-version-information-from-within-your-program"></a>Доступ к сведениям о версии из создаваемой программы

1. Если вы хотите получить доступ к сведениям о версии из создаваемой программы, используйте [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) функции и [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) функции.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редактор сведений о версии](../windows/version-information-editor.md)  
[Сведения о версии (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)