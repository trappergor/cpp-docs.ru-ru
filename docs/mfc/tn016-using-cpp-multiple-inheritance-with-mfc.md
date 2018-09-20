---
title: 'TN016: Использование множественного наследования C++ с MFC | Документация Майкрософт'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.inheritance
dev_langs:
- C++
helpviewer_keywords:
- TN016
- MI (Multiple Inheritance)
- multiple inheritance, MFC support for
ms.assetid: 4ee27ae1-1410-43a5-b111-b6af9b84535d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c0ed5c1bc73f58bec1f9ad0d6a790fe3d3c0239
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444690"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016. Использование множественного наследования C++ с MFC

Эта заметка описывает использование множественное наследование (MI) с Microsoft Foundation Classes. Использование MI не является обязательным с MFC. MI не используется в любые классы MFC и не требуется писать библиотеку классов.

Следующие разделы описывают, как MI влияет на использование общих идиом MFC, а также охватываем ограничений MI. Некоторые из этих ограничений являются общие ограничения C++. Другие накладываются архитектурой MFC.

В конце этого техническое Примечание Вы найдете законченное приложение MFC, которое использует MI.

## <a name="cruntimeclass"></a>CRuntimeClass

Сохранение состояния и механизмы создания динамического объекта MFC использования [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) структуру данных для уникальной идентификации классы. MFC связывает одной из этих структур с каждым из динамических и/или сериализуемых классов в приложении. Эти структуры, инициализируются при запуске приложения с помощью специальных статический объект типа `AFX_CLASSINIT`.

Текущая реализация `CRuntimeClass` не поддерживает сведения о типе среды выполнения MI. Это значит, что MI нельзя использовать в приложении MFC. Тем не менее у вас будет определенные обязанности при работе с объектами, имеющими более чем одного базового класса.

[CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) метод будет неправильно определяет тип объекта, если он имеет несколько базовых классов. Следовательно, нельзя использовать [CObject](../mfc/reference/cobject-class.md) как виртуального базового класса и все вызовы `CObject` член функции, такие как [CObject::Serialize](../mfc/reference/cobject-class.md#serialize) и [новыйCObject::operator](../mfc/reference/cobject-class.md#operator_new)должен иметь квалификаторы область, чтобы этот C++ может устранить неоднозначность вызова соответствующие функции. Если программа использует MI в MFC, класс, содержащий `CObject` базовый класс должен быть класс слева в списке базовых классов.

Альтернативой является использование `dynamic_cast` оператор. Приведение объекта с MI к одному из его базовых классов будет заставить компилятор использовать функции в предоставленный базовый класс. Дополнительные сведения см. в разделе [оператор dynamic_cast](../cpp/dynamic-cast-operator.md).

## <a name="cobject---the-root-of-all-classes"></a>CObject - корне все классы

Все значительные классы являются производными непосредственно или косвенно от класса `CObject`. `CObject` does член данных не, но иметь некоторые функциональные возможности по умолчанию. При использовании MI, будут обычно наследуются из двух или более `CObject`-производные классы. В следующем примере показано, как класс может наследовать от [CFrameWnd](../mfc/reference/cframewnd-class.md) и [CObList](../mfc/reference/coblist-class.md):

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    // ...
};
CListWnd myListWnd;
```

В этом случае `CObject` включено два раза. Это означает, что необходим способ для устранения неоднозначности любая ссылка на `CObject` методы или операторы. **Оператор new** и [оператор delete](../mfc/reference/cobject-class.md#operator_delete) являются двумя операторами, которые должны быть однозначно. Например следующий код вызывает ошибку во время компиляции:

```cpp
myListWnd.Dump(afxDump); // compile time error, CFrameWnd::Dump or CObList::Dump
```

## <a name="reimplementing-cobject-methods"></a>Воссоздание методы CObject

При создании нового класса, имеется два или более `CObject` производные базовые классы следует `CObject` методов, к которым других пользователей. Операторы **новый** и **удалить** являются обязательными и [дампа](../mfc/reference/cobject-class.md#dump) рекомендуется. Следующий пример reimplements **новый** и **удалить** операторы и `Dump` метод:

```cpp
class CListWnd : public CFrameWnd, public CObList
{
public:
    void* operator new(size_t nSize)
    {
        return CFrameWnd:: operator new(nSize);
    }
    void operator delete(void* p)
    {
        CFrameWnd:: operator delete(p);
    }
    void Dump(CDumpContent& dc)
    {
        CFrameWnd::Dump(dc);
        CObList::Dump(dc);
    }
    // ...
};
```

## <a name="virtual-inheritance-of-cobject"></a>Виртуальное наследование от CObject

Может показаться, что практически наследование `CObject` бы устранения неоднозначности функции, но это не так. Так как нет данных члена в `CObject`, виртуальное наследование, чтобы предотвратить несколько копий данных члена базового класса не требуется. В первом примере, показанном выше `Dump` виртуальный метод по-прежнему неоднозначен, так как он реализован по-разному в `CFrameWnd` и `CObList`. Для устранения неоднозначности рекомендуется следовать указаниям, приведенным в предыдущем разделе.

## <a name="cobjectiskindof-and-run-time-typing"></a>CObject::IsKindOf и введя во время выполнения

Механизм среды выполнения ввода, поддерживаемый MFC в `CObject` использует макросы DECLARE_DYNAMIC, IMPLEMENT_DYNAMIC, DECLARE_DYNCREATE, IMPLEMENT_DYNCREATE, DECLARE_SERIAL и IMPLEMENT_SERIAL. Эти макросы можно выполнять проверку типов во время выполнения для обеспечения безопасного приведения.

Эти макросы поддерживает только один базовый класс и будет работать способом для multiply наследуемых классов. Базовый класс, указываемых в IMPLEMENT_DYNAMIC или IMPLEMENT_SERIAL должен быть базовым классом первый (или слева). Такое размещение дает возможность проверить крайняя левая базового класса только тип. Система типов среды выполнения будет знать ничего о дополнительных базовых классов. В следующем примере, сделает систем во время выполнения тип проверки на соответствие `CFrameWnd`, но ничего не будет знать о `CObList`.

```cpp
class CListWnd : public CFrameWnd, public CObList
{
    DECLARE_DYNAMIC(CListWnd)
    // ...
};
IMPLEMENT_DYNAMIC(CListWnd, CFrameWnd)
```

## <a name="cwnd-and-message-maps"></a>CWnd и схемы сообщений

Для системы сопоставления сообщений MFC работал правильно существуют две дополнительные требования:

- Должен существовать только один `CWnd`-производный базовый класс.

- `CWnd`-Производный базовый класс должен быть базовым классом первый (или слева).

Ниже приведены некоторые примеры, которые не будут работать.

```cpp
class CTwoWindows : public CFrameWnd, public CEdit
{ /* ... */ }; // error : two copies of CWnd

class CListEdit : public CObList, public CEdit
{ /* ... */ }; // error : CEdit (derived from CWnd) must be first
```

## <a name="a-sample-program-using-mi"></a>Пример программы, с помощью MI

Следующий пример — это автономное приложение, которое состоит из одного класса, производного от `CFrameWnd` и [CWinApp](../mfc/reference/cwinapp-class.md). Мы не рекомендуем структурировать приложение таким образом, что это пример наименьшее приложения MFC, которое имеет один класс.

```cpp
#include <afxwin.h>

class CHelloAppAndFrame : public CFrameWnd, public CWinApp
{
public:
    CHelloAppAndFrame() {}

    // Necessary because of MI disambiguity
    void* operator new(size_t nSize)
        { return CFrameWnd::operator new(nSize); }
    void operator delete(void* p)
        { CFrameWnd::operator delete(p); }

    // Implementation
    // CWinApp overrides
    virtual BOOL InitInstance();
    // CFrameWnd overrides
    virtual void PostNcDestroy();
    afx_msg void OnPaint();

    DECLARE_MESSAGE_MAP()
};

BEGIN_MESSAGE_MAP(CHelloAppAndFrame, CFrameWnd)
    ON_WM_PAINT()
END_MESSAGE_MAP()

// because the frame window is not allocated on the heap, we must
// override PostNCDestroy not to delete the frame object
void CHelloAppAndFrame::PostNcDestroy()
{
    // do nothing (do not call base class)
}

void CHelloAppAndFrame::OnPaint()
{
    CPaintDC dc(this);
    CRect rect;
    GetClientRect(rect);

    CString s = "Hello, Windows!";
    dc.SetTextAlign(TA_BASELINE | TA_CENTER);
    dc.SetTextColor(::GetSysColor(COLOR_WINDOWTEXT));
    dc.SetBkMode(TRANSPARENT);
    dc.TextOut(rect.right / 2, rect.bottom / 2, s);
}

// Application initialization
BOOL CHelloAppAndFrame::InitInstance()
{
    // first create the main frame
    if (!CFrameWnd::Create(NULL, "Multiple Inheritance Sample",
        WS_OVERLAPPEDWINDOW, rectDefault))
        return FALSE;

    // the application object is also a frame window
    m_pMainWnd = this;
    ShowWindow(m_nCmdShow);
    return TRUE;
}

CHelloAppAndFrame theHelloAppAndFrame;
```

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)
