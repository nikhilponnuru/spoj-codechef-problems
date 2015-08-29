#include <cstdlib>
#include <iostream>
#include <sstream>
 
using namespace std;
 
class Node
{
public:
	Node* morning = NULL;
	Node* night = NULL;
	int age;
 
};
int identicalTrees(struct Node* a, struct Node* b)
{
	/*1. both empty */
	if (a == NULL && b == NULL)
		return 1;
 
	/* 2. both non-empty -> compare them */
	if (a != NULL && b != NULL)
	{
		return
			(
			a->age == b->age &&
			identicalTrees(a->morning, b->morning) &&
			identicalTrees(a->night, b->night)
			);
	}
 
	/* 3. one empty, one not -> false */
	return 0;
}
 
int subtree(Node* x, Node* z)
{
	if (x == NULL)
	{
		return 0;
	}
	else if (z == NULL)
		return 1;
	else
	{
		if (identicalTrees(x, z) == 1) return 1;
		else
		{
			return
				(
			
				subtree(x->morning, z) ||
				subtree(x->night, z)
				);
 
			
		}
	}
 
};
int main(int argc, char *argv[])
{
	int q, m, n;
	n = 0;
	cin >> n;
	Node* T, O;
	Node* arr = new Node[n];
	T = arr;
	for (int i = 0; i<n; i++) {
		cin >> arr[i].age;
	}	Node* x; cin.ignore(20, '\n');
	char s[100];
	string xe;
	stringstream ss(xe);
	int ix = 0;
	do
	{
		int z = 0;
		cin.getline(s, 100);
		int to; int from; char when;
		stringstream ss(s);
		ss >> to;
		ss >> from;
		ss >> when;
		x = arr + (to - 1);
		if (when == 'M')x->morning = arr + (from - 1);
		if (when == 'E')x->night = arr + (from - 1);
		ix++;
	} while (ix<n - 1);
	cin >> q;
	for (int i = 0; i < q; i++)
	{
		cin >> m;
		Node* arrComp = new Node[m]; Node* O; O = arrComp;
		for (int a = 0; a<m; a++) cin >> arrComp[a].age; cin.ignore(20, '\n');
		for (int a = 0; a<m - 1; a++)
		{
			char s[100];
			cin.getline(s, 100); int to; int from; char when;
			istringstream iss(s);
			iss >> to; iss >> from; iss >> when;
			if (when == 'M')arrComp[to - 1].morning = &arrComp[from - 1];
			if (when == 'E')arrComp[to - 1].night = &arrComp[from - 1];
		}
		int x = subtree(T, O);
		if (x == 1)ss << "YES"<<endl;
		else ss << "NO" << endl;
	}
	cout << ss.rdbuf();
	
	return 0;
} 
