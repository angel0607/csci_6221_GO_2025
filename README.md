Required installations

1. VS-Code
2. Docker Desktop
3. GO lang 
4. Node js

VS-code extension:
1. Javascript and Typescript - microsoft
2. Dev Containers
3. Docker
4. ES7 React
5. ESLint
6. Go
7. React Developer Tools
8. SQLite Viewer
9. WSL


Debugging and Running:
React Frontend → http://localhost:3000
Dashboard API → http://localhost:8080/api/alerts & /logs
Blue Team → http://localhost:8081/defend
Red Team → http://localhost:8082/attack

docker-compose down -v
docker-compose build --no-cache
docker-compose up

Front-end:
npm install
npm audit fix --force
npm start
npm run build
cd frontend
  npm start


go run blueteam/main.go
go run redteam/main.go


Verify DB manually :

D:\go-work\GO_project\redblue-sim>docker volume inspect simdata --format '{{.Mountpoint}}'
'/var/lib/docker/volumes/simdata/_data'

D:\go-work\GO_project\redblue-sim>explorer $(docker volume inspect simdata --format '{{.Mountpoint}}')

D:\go-work\GO_project\redblue-sim>docker ps --filter "name=dashboard" --format "{{.ID}}"
21846f44a7d2

D:\go-work\GO_project\redblue-sim>docker exec -it 21846f44a7d2 sh
/app # apk add sqlite
OK: 10 MiB in 20 packages
/app # sqlite3 /data/sim.db
SQLite version 3.41.2 2023-03-22 11:56:21
Enter ".help" for usage hints.
sqlite> .tables
alerts  logs    users