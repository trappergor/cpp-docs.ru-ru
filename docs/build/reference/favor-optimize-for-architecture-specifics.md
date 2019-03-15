---
title: /favor (оптимизация для особенностей архитектуры)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: b914d3e6e7a2865ec610249ff51d320d7890adcb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57820459"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (оптимизация для особенностей архитектуры)

**/ favor:** `option` создается код, оптимизированный для конкретной архитектуры или для специфики микроархитектур в AMD и Intel архитектур.

## <a name="syntax"></a>Синтаксис

> **/ favor:**{**blend** | **ATOM** | **AMD64** | **INTEL64**}

## <a name="remarks"></a>Примечания

**/favor:Blend**<br/>
(x86 и x64) создает код, который оптимизирован для специфики микроархитектур в AMD и Intel архитектур. Хотя **/favor:blend** могут не обеспечивать максимальную производительность возможно для определенного процессора, предназначенный для обеспечения оптимальной производительности для широкого x86 и x64 процессоров. По умолчанию **/favor:blend** в силу.

**/favor:Atom**<br/>
(x86 и x64) создается код, оптимизированный под особенности процессора Intel Atom, а также технологий процессоров Intel Centrino Atom. Код, созданный с помощью **/favor:ATOM** может привести к инструкции Intel SSSE3, SSE3, SSE и SSE2 для процессоров Intel.

**/favor:AMD64**<br/>
(только x64) оптимизирует созданный код для AMD Opteron и Athlon, которые поддерживают 64-разрядных расширениях. Оптимизированный код можно запустить в x64 все совместимые платформы. Код, созданный с помощью **/favor:AMD64** может привести к снижению производительности для процессоров Intel, поддерживающих Intel64.

**/favor:Intel64**<br/>
(только x64) оптимизирует созданный код для процессоров Intel, поддерживающих Intel64, который обычно обеспечивает более высокую производительность для данной платформы. Код может выполняться в любой x64 платформы. Код, созданный с помощью **/favor:INTEL64** может привести к снижению производительности на AMD Opteron и Athlon, которые поддерживают 64-разрядных расширениях.

> [!NOTE]
> Архитектура Intel64 ранее была известна как технология Extended Memory 64, и соответствующий параметр компилятора был **/favor:EM64T**.

Сведения о программировании для x64 архитектуры, см. в разделе [x64 программные соглашения](../x64-software-conventions.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **C/C++** папки.

1. Выберите **командной строки** страницу свойств.

1. Введите параметр компилятора в **Дополнительные параметры** поле.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
