---
title: /GA (Оптимизация для приложений Windows)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: bd6c4a3464762a24c9079bb79318ad3b0f05b74a
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420717"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Оптимизация для приложений Windows)

Результаты в более эффективный код для файла .exe для доступа к переменным локальное хранилище потока (TLS).

## <a name="syntax"></a>Синтаксис

```
/GA
```

## <a name="remarks"></a>Примечания

**/GA** ускоряет доступ к данным объявлен с [__declspec(thread)](../../cpp/declspec.md) в приложении на базе Windows. Если этот параметр имеет значение, [__tls_index](/windows/desktop/ProcThread/thread-local-storage) макрос полагается равным 0.

С помощью **/GA** для библиотеки DLL может привести к созданию неверного кода.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
