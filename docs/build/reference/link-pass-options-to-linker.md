---
title: /link (Передача параметров компоновщику)
ms.date: 03/25/2019
f1_keywords:
- /link
helpviewer_keywords:
- /link compiler option [C++]
- pass options to linker
- link compiler option [C++]
- linker [C++], passing options to
- -link compiler option [C++]
- cl.exe compiler [C++], passing options to linker
ms.assetid: 16902a94-c094-4328-841f-3ac94ca04848
ms.openlocfilehash: 37743e855c933b6236b5e7a837db257f332a3037
ms.sourcegitcommit: bbaf65f8ed1af12828b38f8eacd24f934ac0e538
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2019
ms.locfileid: "67155784"
---
# <a name="link-pass-options-to-linker"></a>/link (Передача параметров компоновщику)

Передает один или несколько параметров компоновщика в компоновщик.

## <a name="syntax"></a>Синтаксис

> **/ link** *параметры компоновщика*

## <a name="arguments"></a>Аргументы

*Параметры компоновщика*<br/>
Параметр компоновщика или параметры для передачи в компоновщик.

## <a name="remarks"></a>Примечания

**/Link** параметр и его параметры компоновщика должны располагаться после имен файлов и параметров CL. Пробел между **/link** и любые параметры компоновщика. Дополнительные сведения см. в разделе [ссылку компоновщика MSVC](linking.md).

## <a name="example"></a>Пример

Компилирует этот пример командной строки *hello.cpp* и связывает ее к существующему файлу объекта *there.obj*. Затем он передает дополнительный **/Version** команду компоновщика:

`cl /W4 /EHsc hello.cpp there.obj /link /VERSION:3.14`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

Интегрированная среда разработки обычно отправляет отдельные команды для компиляции и компоновки кода. Параметры компоновщика можно задать на страницах свойств проекта.

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **компоновщика** папки.

1. Измените одно или несколько свойств. Выберите **ОК** для сохранения внесенных изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
