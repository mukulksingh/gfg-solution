left view of binary tree 



vector<int> leftView(Node *root)
{
    vector<int> ans;
    queue<Node *> q;
    if(root==NULL)
        return ans;
    q.push(root);
    q.push(NULL);
    while(!q.empty()){
        Node *temp=q.front();
        if(temp){
            ans.push_back(temp->data);
            while(q.front()!=NULL){
                if(temp->left)
                    q.push(temp->left);
                if(temp->right)
                    q.push(temp->right);
                q.pop();
                temp=q.front();
            }
            q.push(NULL);
        }
    q.pop();
    }
return ans;
}
 
