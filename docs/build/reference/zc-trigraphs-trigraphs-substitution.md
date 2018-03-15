---
title: "/ Zc: trigraphs (подстановка триграфов) | Документы Microsoft"
ms.custom: 
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5fdc5fc6432335e964a05185b7647b152a57d8f4
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (подстановка триграфов)

Когда **/Zc: trigraphs** указан, компилятор заменяет последовательность символов триграфов, используя соответствующие знаки пунктуации.

## <a name="syntax"></a>Синтаксис

> **/Zc:trigraphs**[**-**]  

## <a name="remarks"></a>Примечания

Объект *триграф* состоит из двух последовательных вопросительных знаков ("??») следуют уникальный третьего знака. Стандарт языка C поддерживает триграфов исходные файлы, использующие набор символов, который не содержит удобных графических представлений некоторых знаков пунктуации. Например, если включены триграфов, компилятор заменяет «?? =» с помощью символа «#». -C ++ 14 триграфов поддерживаются как в C. Стандарт C ++ 17 удаление триграфов из языка C++. В коде C++ **/Zc: trigraphs** параметр компилятора включает подстановка триграфов последовательностей по соответствующим знаком пунктуации. **/Zc:trigraphs-** отключает подстановка триграфов.

**/Zc: trigraphs** параметр выключен по умолчанию, и этот параметр не влияет при [/ разрешительным-](permissive-standards-conformance.md) параметра.

Список триграфов C/C++ и пример их использования см. в разделе [триграфов](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Изменить **Дополнительные параметры** включив **/Zc: trigraphs** или **/Zc:trigraphs-** и выберите **ОК**.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
[Триграфы](../../c-language/trigraphs.md)<br/>
