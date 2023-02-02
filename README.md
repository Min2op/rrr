

using namespace std;


class user{
    private:
    string name;
    string address;
    int age;


public:

    string getName()
    {
        return name;
    }

    string getAddress(){
        return address;
    }

    int getAge(){
        return age;
    }

    void setName(string s, user &u){
        u.name = s;
    }

    void setAddress(string s, user &u){
        u.address = s;
    }

    void setAge(int x, user &u){
        u.age = x;
    }

    void addUser(){
        cout << "Please enter the user Name" << endl;

    }
    };



void outputTofile(vector<user> s){
    ofstream ofile;
    ofile.open("THEBEST.txt", ios::app);

    
    
    for(int i = 0; i <s.size(); i++){
        ofile << s[i].getName();
        ofile << endl;
        ofile << s[i].getAge();
        ofile << endl;
        ofile << s[i].getAddress();
        ofile << endl;


    }


}

int main(){


    vector<user> Users;
    user temp;
    int x = 0;
    string holder;
    for(int i = 0; i < 5; i++){
    cout << "Please enter the user Name" << endl;
    cin >> holder;
    temp.setName(holder, temp);
    cout << "Please enter the users age" << endl;
    cin >> x;
    temp.setAge(x, temp);
    cout << "PLease enter the users address" << endl;
    cin >> holder;
    temp.setAddress(holder, temp);


    Users.push_back(temp);
    
    outputTofile(Users);
    }
    
    
    
    
    return 0;
}
