---
title: '/ Zc: externconstexpr (Включение внешних переменных constexpr)'
ms.date: 02/28/2018
f1_keywords:
- /Zc:externConstexpr
helpviewer_keywords:
- -Zc:externConstexpr compiler option (C++)
- extern constexpr variables (C++)
ms.assetid: 4da5e33a-2e4d-4ed2-8616-bd8f43265c27
ms.openlocfilehash: 3c18a5310646ea39c0599f709e9fddc3990b7a2b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813062"
---
# <a name="zcexternconstexpr-enable-extern-constexpr-variables"></a>/ Zc: externconstexpr (Включение внешних переменных constexpr)

**/Zc: externconstexpr** параметр компилятора компилятор должен соответствовать стандарту C++ и разрешить внешнюю компоновку для `constexpr` переменные. По умолчанию Visual Studio всегда дает `constexpr` внутреннюю компоновку переменной, даже в том случае, если указать `extern` ключевое слово.

## <a name="syntax"></a>Синтаксис

> **/Zc:externConstexpr**[**-**]

## <a name="remarks"></a>Примечания

**/Zc: externconstexpr** компилятора предписывает компилятору для применения к переменным, объявленным с помощью внешней компоновки `extern constexpr`. В более ранних версиях Visual Studio и по умолчанию или если **/Zc:externConstexpr-** указан, Visual Studio применяет внутреннюю компоновку для `constexpr` переменные, даже если `extern` используется ключевое слово. **/Zc: externconstexpr** параметр доступен, начиная с Visual Studio 2017 15.6 обновления. и по умолчанию отключены. [/ Permissive-](permissive-standards-conformance.md) параметр не позволяет включить **/Zc: externconstexpr**.

Если файл заголовка содержит переменную, объявленную `extern constexpr`, он должен быть помечен как [__declspec(selectany)](../../cpp/selectany.md) для объединения повторяющихся объявлений в один экземпляр связанного двоичного файла. В противном случае могут возникнуть ошибки компоновщика, например, LNK2005, нарушения правила одного определения.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Добавить **/Zc: externconstexpr** или **/Zc:externConstexpr-** для **Дополнительные параметры:** области.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](zc-conformance.md)<br/>
[Ключевое слово auto](../../cpp/auto-keyword.md)
