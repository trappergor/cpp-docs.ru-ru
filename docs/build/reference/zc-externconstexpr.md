---
title: "/Zc:externConstexpr (Включить внешние переменные constexpr) | Документы Microsoft"
ms.custom: 
ms.date: 9/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:externConstexpr
dev_langs:
- C++
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 84037e5e8a942d51175d97957d0c05bd6f4aa29d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/Zc:externConstexpr (Включить внешние переменные constexpr)

**/Zc:externConstexpr** компилятора указывает компилятору соответствует стандарту C++, а также позволяют внешней компоновки для `constexpr` переменных. По умолчанию Visual Studio всегда дает `constexpr` переменной внутренней компоновкой, даже в том случае, если указать `extern` ключевое слово.

## <a name="syntax"></a>Синтаксис

> /Zc:externConstexpr [-]

## <a name="remarks"></a>Примечания

**/Zc:externConstexpr** параметр компилятора указывает компилятору на необходимость применить к переменным, объявленным с помощью внешней компоновки `extern constexpr`. **/Zc:externConstexpr** параметр доступен, начиная с Visual Studio 2017 г. обновление 15,5. В более ранних версиях Visual Studio и по умолчанию или если **/Zc:externConstexpr-** указан, Visual Studio применяет внутренней компоновки для `constexpr` переменных, даже если `extern` используется ключевое слово.

Если переменная, объявленная в файле заголовка `extern constexpr`, он должен быть помечен [__declspec(selectany)](../../cpp/selectany.md) для слияния повторяющиеся объявления в один экземпляр связанного двоичного файла. В противном случае могут возникнуть ошибки компоновщика, например, LNK2005, нарушения правила одного определения.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. В разделе **свойства конфигурации**, разверните **C/C++** и выберите **командной строки**.

1. Добавить **/Zc:externConstexpr** или **/Zc:externConstexpr-** для **Дополнительные параметры:** области.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)  
[Ключевое слово auto](../../cpp/auto-keyword.md)