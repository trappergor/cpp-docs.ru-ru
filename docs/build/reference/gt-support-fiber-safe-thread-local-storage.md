---
title: /GT (поддержка локальной памяти потока, безопасной относительно волокон)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
ms.openlocfilehash: 417ac00a446f773a424553e42478a4f0cf58efc6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822520"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (поддержка локальной памяти потока, безопасной относительно волокон)

Поддерживает безопасность волокон для данных, размещаемых с помощью статических локальной памяти потока, то есть данных, размещаемых с `__declspec(thread)`.

## <a name="syntax"></a>Синтаксис

```
/GT
```

## <a name="remarks"></a>Примечания

Данные объявлен с `__declspec(thread)` осуществляется с помощью массива локальное хранилище потока (TLS). Массив TLS представляет собой массив адресов, которые система хранит для каждого потока. Каждый адрес в этом массиве указывает расположение локальной памяти потока данных.

Волокно представляет упрощенный объект, который состоит из стека и контекста регистров и могут быть назначены на различные потоки. Волокно можно запустить в любом потоке. Так как волокно может быть выведено из и перезапустить позже в другом потоке, адрес массива TLS не должен кэшируемых или оптимизируемых как общее подвыражение во время вызова функции (см. в разделе [/Og (виды глобальной оптимизации)](og-global-optimizations.md) для параметра сведения о). **/GT** предотвращает такую оптимизацию.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **оптимизации** страницу свойств.

1. Изменить **включить безопасную относительно волокон оптимизацию** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
