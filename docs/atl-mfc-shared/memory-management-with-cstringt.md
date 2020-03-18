---
title: Управление памятью с помощью CStringT
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: af042c80b9e3e0de872261f89255a26728b218cd
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440502"
---
# <a name="memory-management-with-cstringt"></a>Управление памятью с помощью CStringT

Класс [CStringT](../atl-mfc-shared/reference/cstringt-class.md) — это класс шаблона, используемый для управления символьными строками переменной длины. Память для хранения этих строк выделяется и освобождается через объект диспетчера строк, связанный с каждым экземпляром `CStringT`. MFC и ATL предоставляют экземпляры по умолчанию `CStringT`, называемые `CString`, `CStringA`и `CStringW`, которые управляют строками различных типов символов. Эти типы символов имеют тип TCHAR, **char**и `wchar_t`соответственно. Эти строковые типы по умолчанию используют диспетчер строк, который выделяет память из кучи процесса (в ATL) или кучи CRT (в MFC). Для типичных приложений эта схема выделения памяти достаточно велика. Однако для кода, выполняющего интенсивное использование строк (или многопоточного кода), стандартные диспетчеры памяти могут работать не оптимально. В этом разделе описывается, как переопределить поведение управления памятью по умолчанию для `CStringT`, создавая специально оптимизированные распределителя для поставленной задачи.

- [Реализация пользовательского диспетчера строк (базовый метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Избежание состязания за кучу](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Реализация пользовательского диспетчера строк (расширенный метод)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: пример пользовательского диспетчера строк](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>См. также раздел

[Пример Кустомстринг](../overview/visual-cpp-samples.md)
