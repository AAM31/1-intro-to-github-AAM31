
#include <iostream>
#include <map>
#include <set>
#include <string>

using namespace std;

int main() {
	int n; cin >> n;
	map <string, set<string>> syn;
	for (int i = 0; i < n; i++) {
		string op; cin >> op;

		if (op == "ADD") {
			string a, b; cin >> a; cin >> b;
			syn[a].insert(b);
			syn[b].insert(a);
		}
		if (op == "COUNT") {
			string a; cin >> a;
			cout << syn[a].size() << endl;
		}
		if (op == "CHECK") {
			string a, b; cin >> a; cin >> b;
			bool fl = 0;
			for (const auto& item : syn[a]) {
				if (item == b) {fl = 1;}
			}
			if (fl){
				cout << "YES" << endl;
			}
			else{ 
				cout << "NO" << endl; 
			}
		}
	}
	system("pause");
	return 0;
}
