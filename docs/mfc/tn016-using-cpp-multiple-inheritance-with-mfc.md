---
title: 'TN016: Использование множественного наследования C++ с MFC | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: fe1e79324c4c1f7408e1b801cf2be581b9884717
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384092"
---
# <a name="tn016-using-c-multiple-inheritance-with-mfc"></a>TN016. Использование множественного наследования C++ с MFC
Эта заметка описывается использование множественного наследования (ИУП) с помощью классов Microsoft Foundation. Использование MI не требуется в MFC. MI не используется в любые классы MFC и не требуется писать библиотеки классов.  
  
 Следующие подразделы описывают, как MI влияет на использование общих идиом MFC, а также охватываются ограничения MI. Некоторые из этих ограничений, общие ограничения C++. Другие применяются для архитектуры MFC.  
  
 В конце этого техническое Примечание обнаружится законченное приложение MFC, которое использует мн.  
  
## <a name="cruntimeclass"></a>CRuntimeClass  
 Сохранение состояния и механизмы создания динамического объекта использования MFC [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) структуру данных для уникальной идентификации классов. MFC связывает одной из этих структур с каждым классом динамические или сериализуемым в приложении. Эти структуры инициализируются при запуске приложения с помощью специальных статический объект типа `AFX_CLASSINIT`.  
  
 Текущая реализация `CRuntimeClass` поддерживает MI сведения о типе среды выполнения. Это значит, что MI нельзя использовать в приложении MFC. Тем не менее будет иметь некоторые обязанности при работе с объектами, имеющими более чем одного базового класса.  
  
 [CObject::IsKindOf](../mfc/reference/cobject-class.md#iskindof) метод будет неправильно определяет тип объекта, если он имеет несколько базовых классов. Следовательно, нельзя использовать [CObject](../mfc/reference/cobject-class.md) как виртуального базового класса и все вызовы `CObject` члена функции, такие как [CObject::Serialize](../mfc/reference/cobject-class.md#serialize) и [новыйCObject::operator](../mfc/reference/cobject-class.md#operator_new)должен иметь квалификаторы области, так что C++ устранить неоднозначность вызов соответствующей функции. Если программа использует MI в MFC, класс, содержащий `CObject` базовый класс должен быть классом слева в списке базовых классов.  
  
 Альтернативой является использование `dynamic_cast` оператор. Приведение объекта с MI к одному из его базовых классов приведет к компилятору использовать функции в указанный базовый класс. Дополнительные сведения см. в разделе [оператор dynamic_cast](../cpp/dynamic-cast-operator.md).  
  
## <a name="cobject---the-root-of-all-classes"></a>CObject - корня для всех классов  
 Прямо или косвенно наследующие все значимые классы от класса `CObject`. `CObject` does не имеет член данных, но у него некоторые функциональные возможности по умолчанию. При использовании MI будет обычно наследуются из двух или более `CObject`-производные классы. В следующем примере показано, как класс может наследовать от [CFrameWnd](../mfc/reference/cframewnd-class.md) и [CObList](../mfc/reference/coblist-class.md):  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
 ...  
};  
CListWnd myListWnd;  
```  
  
 В этом случае `CObject` входит в два раза. Это означает, что вам необходим способ для устранения неоднозначности ссылки на `CObject` методов и операторов. `operator new` И [оператор delete](../mfc/reference/cobject-class.md#operator_delete) являются два оператора, которые можно устранить неоднозначность. Например следующий код вызывает ошибку во время компиляции:  
  
```  
myListWnd.Dump(afxDump);
*// compile time error, CFrameWnd::Dump or CObList::Dump   
```  
  
## <a name="reimplementing-cobject-methods"></a>Воссоздание методы CObject  
 При создании нового класса, который имеет два или более `CObject` базовых классов, производных следует реализовать `CObject` методы, которые вы хотите других пользователей. Операторы `new` и `delete` являются обязательными и [дампа](../mfc/reference/cobject-class.md#dump) рекомендуется. Следующий пример reimplements `new` и `delete` операторы и `Dump` метод:  
  
```  
class CListWnd : public CFrameWnd, public CObList  
{  
public:  
    void* operator new(size_t nSize)  
 { return CFrameWnd:: operator new(nSize);

}  
    void operator delete(void* p)  
 { CFrameWnd:: operator delete(p);

}  
 
    void Dump(CDumpContent& dc)  
 { CFrameWnd::Dump(dc);

    CObList::Dump(dc);

} 
 ...  
};  
```  
  
## <a name="virtual-inheritance-of-cobject"></a>Виртуальное наследование от CObject  
 Может показаться, что практически наследование `CObject` бы устранить неоднозначность функции, но это не так. Так как нет данных члена в `CObject`, виртуальное наследование, чтобы предотвратить несколько копий данных члена базового класса не требуется. В первом примере, показанном выше `Dump` виртуальный метод по-прежнему неоднозначен, так как она реализована по-разному в `CFrameWnd` и `CObList`. Для устранения неоднозначности рекомендуется следовать инструкциям, представленных в предыдущем разделе.  
  
## <a name="cobjectiskindof-and-run-time-typing"></a>CObject::IsKindOf и введя во время выполнения  
 Механизм среды выполнения ввода, поддерживаемый MFC в `CObject` использует макросы `DECLARE_DYNAMIC`, `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE`, `IMPLEMENT_DYNCREATE`, `DECLARE_SERIAL` и `IMPLEMENT_SERIAL`. Эти макросы можно выполнять проверку типов во время выполнения для обеспечения безопасного downcasts.  
  
 Эти макросы поддерживает только один базовый класс и будет работать ограниченно для умножить наследуемых классов. Базовый класс, укажите в `IMPLEMENT_DYNAMIC` или `IMPLEMENT_SERIAL` должен быть базовым классом первый (или слева). Такое размещение позволит проверить слева базового класса только тип. Система типов во время выполнения будет ничего не знаете о дополнительных базовых классов. В следующем примере системы во время выполнения будет выполнять проверку для типа `CFrameWnd`, но нет никаких данных о `CObList`.  
  
```  
class CListWnd : public CFrameWnd,
    public CObList  
{  
    DECLARE_DYNAMIC(CListWnd) 
 ...  
};  
IMPLEMENT_DYNAMIC(CListWnd,
    CFrameWnd)  
```  
  
## <a name="cwnd-and-message-maps"></a>CWnd и схемы сообщений  
 Для системы карты сообщений MFC работал правильно существует два дополнительных требований:  
  
-   Должен существовать только один `CWnd`-производного базового класса.  
  
-   `CWnd`-Базового производного класса должен быть базовым классом первый (или слева).  
  
 Ниже приведены некоторые примеры, которые не будут работать.  
  
```  
class CTwoWindows : public CFrameWnd,
    public CEdit  
 { ... }; *// error : two copies of CWnd  
 
class CListEdit : public CObList,
    public CEdit  
 { ... }; *// error : CEdit (derived from CWnd) must be first  
```  
  
## <a name="a-sample-program-using-mi"></a>Пример программы, с помощью MI  
 Следующий пример — это автономное приложение, которое состоит из одного класса, производного от `CFrameWnd` и [CWinApp](../mfc/reference/cwinapp-class.md). Не рекомендуется структурировать приложение таким образом, что это пример наименьшее приложения MFC, который имеет один класс.  
  
```  
#include <afxwin.h>  
  
class CHelloAppAndFrame : public CFrameWnd, public CWinApp  
{   
public:  
    CHelloAppAndFrame()  
        { }  
  
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
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

