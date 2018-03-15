---
title: "/Zc:externConstexpr (Включить внешние переменные constexpr) | Документы Microsoft"
ms.custom: 
ms.date: 02/28/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6597bc96609ab051df56886ccc580516986f97ed
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (Включить внешние переменные constexpr)

**/Zc:externConstexpr** компилятора указывает компилятору соответствует стандарту C++, а также позволяют внешней компоновки для `constexpr` переменных. По умолчанию Visual Studio всегда дает `constexpr` переменной внутренней компоновкой, даже в том случае, если указать `extern` ключевое слово.

## <a name="syntax"></a>Синтаксис

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>Примечания

**/Zc:externConstexpr** параметр компилятора указывает компилятору на необходимость применить к переменным, объявленным с помощью внешней компоновки `extern constexpr`. В более ранних версиях Visual Studio и по умолчанию или если **/Zc:externConstexpr-** указан, Visual Studio применяет внутренней компоновки для `constexpr` переменных, даже если `extern` используется ключевое слово. **/Zc:externConstexpr** параметр доступен, начиная с Visual Studio 2017 г. обновление 15,6. и по умолчанию отключена. [/ Разрешительным-](permissive-standards-conformance.md) параметр не позволяет включить **/Zc:externConstexpr**.

Если переменная, объявленная в файле заголовка `extern constexpr`, он должен быть помечен [__declspec(selectany)](../../cpp/selectany.md) для слияния повторяющиеся объявления в один экземпляр связанного двоичного файла. В противном случае могут возникнуть ошибки компоновщика, например, LNK2005, нарушения правила одного определения.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Добавить **/Zc:externConstexpr** или **/Zc:externConstexpr-** для **Дополнительные параметры:** области.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)  
[Ключевое слово auto](../../cpp/auto-keyword.md)