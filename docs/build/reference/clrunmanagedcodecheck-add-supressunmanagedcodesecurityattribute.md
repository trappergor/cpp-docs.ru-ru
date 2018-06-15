---
title: / Параметр CLRUNMANAGEDCODECHECK (Добавление атрибута SupressUnmanagedCodeSecurityAttribute) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
dev_langs:
- C++
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d0a70ea74851d3a10f9d46b8289098d6fb3fe22
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705378"
---
# <a name="clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute"></a>Параметр /CLRUNMANAGEDCODECHECK (добавление атрибута SupressUnmanagedCodeSecurityAttribute)

**/ Параметр CLRUNMANAGEDCODECHECK** указывает, будет ли компоновщик применять <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> с компоновщиком `PInvoke` вызовы из управляемого кода в собственные библиотеки DLL.

## <a name="syntax"></a>Синтаксис

> **/ ПАРАМЕТР CLRUNMANAGEDCODECHECK**[**: НЕТ**]

## <a name="remarks"></a>Примечания

По умолчанию компоновщик применяет **SuppressUnmanagedCodeSecurityAttribute** с компоновщиком `PInvoke` вызовов. Когда **/clrunmanagedcodecheck** , **SuppressUnmanagedCodeSecurityAttribute** не применяется.

Компоновщик только добавляет атрибут к объектам, которые были скомпилированы с **/CLR** или **/CLR: pure**. Тем не менее **/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017 г.

Объект `PInvoke` вызов создается компоновщиком, когда компоновщик не удается найти управляемый символ, удовлетворяющий ссылке от управляемого вызывающего объекта, но можно найти символ для удовлетворения этой ссылки. Дополнительные сведения о `PInvoke`, в разделе [вызов собственных функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md).

Обратите внимание, что при использовании <xref:System.Security.AllowPartiallyTrustedCallersAttribute> в коде, необходимо явно задать **/clrunmanagedcodecheck**. Если изображение содержит атрибуты SuppressUnmanagedCodeSecurity и AllowPartiallyTrustedCallers не потенциальной уязвимости безопасности.

В разделе [правила написания безопасного кода для неуправляемого кода](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) Дополнительные сведения о последствиях использования **SuppressUnmanagedCodeSecurityAttribute**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните **свойства конфигурации** узла.

1. Разверните **компоновщика** узла.

1. Выберите **Дополнительно** страницу свойств.

1. Изменить **проверьте неуправляемый код CLR** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)
