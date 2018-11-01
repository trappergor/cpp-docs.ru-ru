---
title: /Zc:trigraphs (подстановка триграфов)
ms.date: 03/06/2018
f1_keywords:
- /Zc
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
ms.openlocfilehash: 24f5ba7666e6b4a39787b9edac53142cdd1cd149
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587048"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (подстановка триграфов)

Когда **/Zc: trigraphs** указан, компилятор заменяет триграф последовательности символов, с помощью соответствующим знаком пунктуации.

## <a name="syntax"></a>Синтаксис

> **/ Zc: trigraphs**[**-**]

## <a name="remarks"></a>Примечания

Объект *триграф* состоит из двух последовательных вопросительных знаков ("??») следует третий уникальный знак. Стандарт языка C поддерживает триграфов для исходных файлов, которые используют набор символов, который не содержит удобных графических представлений некоторых знаков пунктуации. Например, если включены триграфов, компилятор заменяет «?? =» с помощью символа «#». До C ++ 14 триграфов поддерживаются как в языке C. Стандарт C ++ 17 удаляет триграфы из языка C++. В коде C++ **/Zc: trigraphs** параметр компилятора включает замену последовательностей триграфов, соответствующим знаком пунктуации. **/Zc:trigraphs-** отключает подстановку триграфов.

**/Zc: trigraphs** параметр отключен по умолчанию, и этот параметр не влияет, когда [/ permissive-](permissive-standards-conformance.md) параметра.

Список триграфов C/C++ и пример, в котором показано, как использовать триграфов, см. в разделе [триграфов](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** свойство **/Zc: trigraphs** или **/Zc:trigraphs-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
[Триграфы](../../c-language/trigraphs.md)<br/>
