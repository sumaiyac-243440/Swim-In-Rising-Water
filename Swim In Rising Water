class Solution {
public:
    int swimInWater(vector<vector<int>>& grid) {

        int n = grid.size();

        vector<vector<int>> dist(n, vector<int>(n, INT_MAX));

        priority_queue<
            pair<int, pair<int,int>>,
            vector<pair<int, pair<int,int>>>,
            greater<pair<int, pair<int,int>>>
        > pq;

        dist[0][0] = grid[0][0];
        pq.push({grid[0][0], {0, 0}});

        int dx[] = {-1, 1, 0, 0};
        int dy[] = {0, 0, -1, 1};

        while (!pq.empty()) {

            auto cur = pq.top();
            pq.pop();

            int t = cur.first;
            int x = cur.second.first;
            int y = cur.second.second;

            if (x == n - 1 && y == n - 1)
                return t;

            if (t > dist[x][y])
                continue;

            for (int i = 0; i < 4; i++) {

                int nx = x + dx[i];
                int ny = y + dy[i];

                if (nx >= 0 && nx < n && ny >= 0 && ny < n) {

                    int nt = max(t, grid[nx][ny]);

                    if (nt < dist[nx][ny]) {
                        dist[nx][ny] = nt;
                        pq.push({nt, {nx, ny}});
                    }
                }
            }
        }

        return -1;
    }
};
