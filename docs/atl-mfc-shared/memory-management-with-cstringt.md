---
title: Управление памятью с помощью CStringT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8676626c47471c2d1702d49df3069b618cc3ff4f
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752210"
---
# <a name="memory-management-with-cstringt"></a>Управление памятью с помощью CStringT

Класс [CStringT](../atl-mfc-shared/reference/cstringt-class.md) — это класс шаблона, используемый для работы со строками знаков переменной длины. Выпущенных при помощи диспетчера строковый объект, связанный с каждым экземпляром и выделения памяти для хранения этих строк `CStringT`. MFC и ATL предоставляют экземпляров по умолчанию `CStringT`, который называется `CString`, `CStringA`, и `CStringW`, который работы со строками из разных символьных типов. Эти типы символов имеют тип TCHAR, **char**, и `wchar_t`, соответственно. Эти строковые типы по умолчанию использовать диспетчер строки, который выделяет память из кучи процесса (в ATL) или кучи CRT (в MFC). Эта схема выделения памяти достаточно для типичных приложений. Однако для кода, что делает с большим объемом используйте строки (или многопоточном коде), диспетчеры памяти по умолчанию может работать медленнее. В этом разделе описывается, как переопределить значение по умолчанию поведение управления памятью `CStringT`, в частности Создание Распределители оптимизированных для поставленной задачи.

- [Реализация пользовательского диспетчера строк (базовый метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Избежание состязания за кучу](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Реализация пользовательского диспетчера строк (расширенный метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: Пример пользовательского диспетчера строк](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>См. также

[Образце CustomString](../visual-cpp-samples.md)

