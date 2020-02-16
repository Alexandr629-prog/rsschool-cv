# RESUME

  
  

1. Askladovich Aliaksandr
2. e-mail: aaskaldovic@gmail.com; phone: +375-(29)-819-94-69
3. EPAM is one of the leading it companies. RS-School is a great opportunity to get good experience in the field of web development, as well as get good experience from specialists in this field. I am a hard-working and stress-resistant person, and I have a great desire to learn programming every day.
4. Middle level C++, beginner level in JavaScript / HTML / CSS
5. Stack:
```
struct List
{
	int x;                                              
	List *Next;
}*Head;


void Add(int x)
{
	List *temp = new List;                             
	temp->x = x;                                        
	temp->Next = Head;                         
	Head = temp;                               
}


void Show()                                
{
	List *temp = Head;                          
	while (temp != NULL)                                
	{
		cout << temp->x<<' ';
		temp = temp->Next;                             
	}
}


void ShowOtr()
{
	List *temp = Head;
	while (temp != NULL)
	{
		if (temp->x < 0)
		{
			cout << "Negative element" << endl; 
			break;
		}
		else temp = temp->Next;
		
	}
}


void izm(List *max, List *min)
{
	List *maxs=Head;
	List *mins=Head;
	List *t;
	if (Head == max)  // Если максимальный элемент первый
	{
		while (mins->Next != min) mins = mins->Next;
		t = Head;
		Head = mins->Next;
		mins->Next = t;
		t = Head->Next;
		Head->Next = max->Next;
		mins->Next->Next = t;

	}
	else if (Head == min)  // Если минимальный элемент первый 
	{
		while (maxs->Next != max) maxs = maxs->Next;
		t = Head;
		Head = maxs->Next;
		maxs->Next = t;
		t = Head->Next;
		Head->Next = min->Next;
		maxs->Next->Next = t;
	}
	else   // Для всех остальных случаев
	{
		while (maxs->Next != max) maxs = maxs->Next;
		while (mins->Next != min) mins = mins->Next;
		t = maxs->Next;
		maxs->Next = mins->Next;
		mins->Next = t;
		maxs = max->Next;
		mins = min->Next;
		max->Next = mins;
		min->Next = maxs;
	}
	
	
	
	
	
}


void ClearList()
{
	while (Head != NULL)                        
	{
		List *temp = Head->Next;                    
		delete Head;                                
		Head = temp;                                
	}
}

int main()
{
	
	int x,n;
	cin >> n;
	Head = NULL; 
	for (int i = 0; i < n; i++)
	{
		cin >> x;
		Add(x); 
	}
	/*Add(-100);*/
	Show(); 
	ShowOtr();
	List *t = Head->Next, *max =Head, *min = Head;
	do
	{
		if (max->x < t->x) max = t;
		if ((min->x > t->x)) min = t;
	}while(t = t->Next);
	izm(max, min);
	cout << endl;
	Show();
	ClearList(); 
	delete Head;
}
```
6. --
7. I'm a second-year student at BSUIR. Completed stepik courses in Javascript and HTML / CSS.