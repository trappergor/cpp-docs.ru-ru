---
title: /CLRUNMANAGEDCODECHECK (удалить атрибут SuppressUnmanagedCodeSecurityAttribute)
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- /CLRUNMANAGEDCODECHECK
helpviewer_keywords:
- -CLRUNMANAGEDCODECHECK linker option
- /CLRUNMANAGEDCODECHECK linker option
ms.assetid: 73abc426-dab0-45e2-be85-0f9a14206cc2
author: corob-msft
ms.author: corob
ms.openlocfilehash: ecc560673a8e98752289ef0e0f89d3abfc1938e4
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837243"
---
# <a name="clrunmanagedcodecheck-remove-suppressunmanagedcodesecurityattribute"></a>/CLRUNMANAGEDCODECHECK (удалить атрибут SuppressUnmanagedCodeSecurityAttribute)

Параметр **/CLRUNMANAGEDCODECHECK** определяет, будет ли компоновщик применять атрибут <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> к созданным компоновщиком вызовам `PInvoke` из управляемого кода в библиотеки DLL машинного кода.

## <a name="syntax"></a>Синтаксис

> **/CLRUNMANAGEDCODECHECK**[ **:NO**]

## <a name="remarks"></a>Примечания

По умолчанию компоновщик применяет атрибут **SuppressUnmanagedCodeSecurityAttribute** к создаваемым им вызовам `PInvoke`. Если параметр включен **/CLRUNMANAGEDCODECHECK**, атрибут **SuppressUnmanagedCodeSecurityAttribute** удаляется. Чтобы явно применить атрибут **SuppressUnmanagedCodeSecurityAttribute** к вызовам `PInvoke`, создаваемым компоновщиком, можно использовать параметр **/CLRUNMANAGEDCODECHECK:NO**.

Компоновщик добавляет этот атрибут только к объектам, скомпилированным с использованием **/clr** или **/clr:pure**. Однако параметр компилятора **/clr:pure** не рекомендуется использовать в Visual Studio 2015 и не поддерживается в Visual Studio 2017 и более поздних версий.

Вызов `PInvoke` создается компоновщиком, когда ему не удается найти управляемый символ, соответствующий ссылке из управляемого вызывающего объекта, но удается найти собственный символ, соответствующий этой ссылке. Дополнительные сведения о `PInvoke` см. в статье [Вызов встроенных функций из управляемого кода](../../dotnet/calling-native-functions-from-managed-code.md).

Имейте в виду, что если в коде используется <xref:System.Security.AllowPartiallyTrustedCallersAttribute>, следует явным образом указать параметр **/CLRUNMANAGEDCODECHECK**, чтобы удалить атрибут **SuppressUnmanagedCodeSecurity**. Одновременное наличие атрибутов **SuppressUnmanagedCodeSecurity** и **AllowPartiallyTrustedCallers** в образе может приводить к уязвимости системы безопасности.

Дополнительные сведения о последствиях использования атрибута **SuppressUnmanagedCodeSecurityAttribute** см. в статье [Руководства по написанию безопасного неуправляемого кода](/dotnet/framework/security/secure-coding-guidelines-for-unmanaged-code).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Разверните узел **Свойства конфигурации**.

1. Разверните узел **Компоновщик**.

1. Выберите страницу свойств **Дополнительно**.

1. Измените значение свойства **Проверка CLR на неуправляемый код**.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRUnmanagedCodeCheck%2A>.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)
