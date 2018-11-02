---
title: / Параметр CLRUNMANAGEDCODECHECK (Remove SuppressUnmanagedCodeSecurityAttribute)
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.openlocfilehash: 3cefe34eef1a30274ba2e9e362e2f61458f10e38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565923"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/ Параметр CLRUNMANAGEDCODECHECK (Remove SuppressUnmanagedCodeSecurityAttribute)

**/ Параметр CLRUNMANAGEDCODECHECK** указывает, что компоновщик не применяется <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> до компоновщиком `PInvoke` вызовы собственных библиотек DLL из управляемого кода.

## <a name="syntax"></a>Синтаксис

> **/ ПАРАМЕТР CLRUNMANAGEDCODECHECK**[**: НЕТ**]

## <a name="remarks"></a>Примечания

По умолчанию компоновщик применяет **SuppressUnmanagedCodeSecurityAttribute** до компоновщиком `PInvoke` вызовов. Когда **/clrunmanagedcodecheck** , **SuppressUnmanagedCodeSecurityAttribute** удаляется. Для явного применения **SuppressUnmanagedCodeSecurityAttribute** до компоновщиком `PInvoke` вызовов, можно использовать **/CLRUNMANAGEDCODECHECK:NO**.

Компоновщик только добавляет атрибут к объектам, которые компилируются с помощью **/CLR** или **/CLR: pure**. Тем не менее **/CLR: pure** параметр компилятора в Visual Studio 2015 не рекомендуется и не поддерживается в Visual Studio 2017.

Объект `PInvoke` компоновщиком создается вызов, когда компоновщик не может найти управляемый символ для удовлетворения ссылку из управляемого вызывающего объекта, но можно найти символ для удовлетворения этой ссылки. Дополнительные сведения о `PInvoke`, см. в разделе [вызов собственных функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md).

Обратите внимание, что при использовании <xref:System.Security.AllowPartiallyTrustedCallersAttribute> в коде, необходимо явно указать **/clrunmanagedcodecheck** удаляемый **SuppressUnmanagedCodeSecurity** атрибута. Это потенциальной уязвимости безопасности, если изображение содержит оба **SuppressUnmanagedCodeSecurity** и **AllowPartiallyTrustedCallers** атрибуты.

См. в разделе [правил написания безопасного кода для неуправляемого кода](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code) Дополнительные сведения о последствиях с помощью **SuppressUnmanagedCodeSecurityAttribute**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните **компоновщика** узла.

1. Выберите **Дополнительно** страницу свойств.

1. Изменить **CLR неуправляемый код проверять** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)
