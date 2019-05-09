# elasticsearch

https://www.elastic.co/guide/en/elasticsearch/client/net-api/5.x/index.html

https://devadventures.net/2018/04/16/connect-your-asp-net-core-application-to-elasticsearch-using-nest-5/

https://www.dotnetcurry.com/aspnet/1354/elastic-search-kibana-in-docker-dotnet-core-app

https://miroslavpopovic.com/posts/2018/07/elasticsearch-with-aspnet-core-and-docker

https://github.com/elastic/elasticsearch-net

// flatMap is how we handle dependencies between observables
  getFlatMap(): Observable<Candidate[]> {
    const observableOne$ = this.getSuggestionsWithoutLocation('coffee');
    return observableOne$.pipe(
      flatMap((suggestions: Suggestion[]) => {
        suggestions.filter(s => s.isCollection);
        return this.findAddressCandidates(suggestions[0].text, suggestions[0].magicKey);
      })
    );
  }
