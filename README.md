#include<iostream>
#include<unordered_map>
using namespace std;
 
class Node {
public:
	char ch;
	bool isTerminal;
	unordered_map<char, Node*> children;
	Node(char ch) {
		this->ch = ch;
		this->isTerminal = false;
	}
};
 
class Trie {
	Node *root;
 
	Trie() {
		this->root = new Node('\0');
	}
 
	void insert(string str) {
		Node *temp = root;
		for(int i = 0; i < str.size(); i++) {
			char ch = str[i];
			if(temp->children.count(ch)) {
				// found the child
				temp = temp->children[ch];
			} else {
				Node *n = new Node(ch);
				temp->children[ch] = n;
				temp = n;
			}
		}
		temp->isTerminal = true;
		return;
	}
 
 
 
};
 
int main(int argc, char const *argv[])
{
 
	return 0;
}
